---
layout: post
title:  Example of check_scalar Function Contribution in scikit-learn
description: In this example, learn to refactor code and add tests in scikit-learn.
date:   2021-12-12 15:01:35 +0300
image:  '/images/blogs/check_scalar.png'
tags:   [opensource, scikit-learn, python]
---

Author:  [Reshama Shaikh](https://reshamas.github.io)  

## Introduction

Use the function [`check_scalar`](https://scikit-learn.org/dev/modules/generated/sklearn.utils.check_scalar.html?highlight=check_scalar#sklearn.utils.check_scalar) for parameters validation. The validation function checks to see the following for a parameter: is an acceptable data type, is within the range of values, the range of values ([interval](https://www.basic-mathematics.com/interval-notation.html)).

- References Issue [#21927](https://github.com/scikit-learn/scikit-learn/issues/21927) (@reshamas)
- References Issue [#20724](https://github.com/scikit-learn/scikit-learn/issues/20724): "Use check_scalar for parameters validation" (with notes by @glemaitre, @jjerphan, @genvalen)
- References PR [#20723](https://github.com/scikit-learn/scikit-learn/pull/20723).  "MNT use check_scalar to validate scalar in AffinityPropagation". This is an example PR by @glemaitre.

A helper function exists in scikit-learn which validates a scalar value: `sklearn.utils.check_scalar` [documentation](https://scikit-learn.org/stable/modules/generated/sklearn.utils.check_scalar.html). 
It is used to validate parameters of classes (and functions). Most of the current classes in scikit-learn do not use this helper function.  We want to refactor the code so that it does use this standard helper function. Utilizing this helper function will help to get consistent error types and messages.

## Steps
Below, I go through an example, step by step.  

### Go to working directory
```bash
pwd
```
```bash
▶ pwd
/Users/reshamashaikh/software-build/scikit-learn
(base) 
~/software-build/scikit-learn  main ✔    
```

### Activate virtual environment
```bash
conda activate sklearndev
```

```bash
▶ conda activate sklearndev
(sklearndev) 
~/software-build/scikit-learn  main ✔    
```
### Sync local repo with the GitHub repo, `main` branch
```bash
git pull upstream main
git push origin main
```

```bash
▶ git pull upstream main
From github.com:scikit-learn/scikit-learn
 * branch                main       -> FETCH_HEAD
Already up to date.
(sklearndev) 
~/software-build/scikit-learn  main ✔                                                                    1d  
▶ git push origin main
Everything up-to-date
(sklearndev) 
~/software-build/scikit-learn  main ✔                                                                    1d  
▶ 
```

### Create a new working branch, from `main` branch
```bash
git checkout main
git checkout -b xscalar_glm
```
```bash
▶ git checkout main
Already on 'main'
Your branch is up to date with 'origin/main'.
(sklearndev) 
~/software-build/scikit-learn  main ✔                                                                    1d  
▶ git checkout -b xscalar_glm
Switched to a new branch 'xscalar_glm'
(sklearndev) 
~/software-build/scikit-learn  xscalar_glm ✔                                                             1d  
▶ 
```

### Identify a class to implement `check_scalar` function

To find an algorithm which may need to implement `check_scalar` function, I searched the repo [scikit-learn/scikit-learn](https://github.com/scikit-learn/scikit-learn) for `max_iter`, as a start. I found a constructor that has scalar numeric as parameters.

I found:  
- File: [sklearn/linear_model/glm.py](https://github.com/scikit-learn/scikit-learn/blob/efa5e3eee5dfa696cc46d462cf20bdf1c95e75cc/sklearn/linear_model/_glm/glm.py)
- Associated test: [sklearn/linear_model/_glm/tests/test_glm.py](https://github.com/scikit-learn/scikit-learn/blob/efa5e3eee5dfa696cc46d462cf20bdf1c95e75cc/sklearn/linear_model/_glm/tests/test_glm.py)

### Identify the scalar numeric parameters

For [glm.py](https://github.com/scikit-learn/scikit-learn/blob/efa5e3eee5dfa696cc46d462cf20bdf1c95e75cc/sklearn/linear_model/_glm/glm.py), I found four classes in the file:    
- `GeneralizedLinearRegressor`
- `PoissonRegressor`
- `GammaRegressor`
- `TweedieRegressor`

I will begin work on the first one, `GeneralizedLinearRegressor`. Also, for each I will look at minimum and maximum values. If minimum and maximum values are missing, I will add them, as well as the boundary conditions.

Within the class `GeneralizedLinearRegressor`, I identify the following scalar numeric parameters:  
1. `alpha`, value range: `[0.0, inf)`
1. `max_iter`, value range: `[1, inf)`
1. `tol`, value range: `(0.0, inf)`
1. `verbose`, value range: `[1, inf)`


## Tests

### Tests and validation

Parameter validation checks are added in order to catch any invalid parameter values passed into the estimator before the algorithm is run. If no parameter validation exists, we are left to the mercy of the algorithm. For instance, if the algorithm receives a negative number for maximum number of iterations, it will break.

Sklearn has thorough validation checks. With the use of the helper function, `check_scalar`, these validation checks can be refactored for greater consistency and readability.

Tests are added to make sure that parameter validation checks behave correctly. In the case of creating tests for `check_scalar`, the tests check that the `check_scalar` validation raises a `ValueError` or a `TypeError` where appropriate, and that the error message returned is as expected.

If no tests exists for the parameter validation, add tests.  Note that even if the tests do not exist, the validation definitely does.



### See if tests exists

In the file [test_glm.py](https://github.com/scikit-learn/scikit-learn/blob/efa5e3eee5dfa696cc46d462cf20bdf1c95e75cc/sklearn/linear_model/_glm/tests/test_glm.py), I see the following test exists. It checks 5 possible inputs, but has only one `ValueError` error message:

```python
@pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
def test_glm_max_iter_argument(max_iter):
    """Test GLM for invalid max_iter argument."""
    y = np.array([1, 2])
    X = np.array([[1], [2]])
    glm = GeneralizedLinearRegressor(max_iter=max_iter)
    with pytest.raises(ValueError, match="must be a positive integer"):
        glm.fit(X, y)
```

In this case, these are invalid values for `max_iter`: `["not a number", 0, -1, 5.5, [1]]`  
- "not a number": invalid type (string), should be integer
- 5.5: invalid type (float), should be integer
- `[1]`: invalid type (list), should be integer
- 0: iterations should be > 0
- -1: iterations should be > 0

So, here we have 5 tests to run. And, our tests should give informative error messages.  

In the `glm.py` file, I temporarily comment out whatever checks exist for valid values (validation) of `max_iter`.  
```python
        # if not isinstance(self.max_iter, numbers.Integral) or self.max_iter <= 0:
        #     raise ValueError(
        #         "Maximum number of iteration must be a positive "
        #         "integer;"
        #         " got (max_iter={0!r})".format(self.max_iter)
        #     )
```

Then, I run the existing test `test_glm_max_iter_argument`:  
```bash
pytest sklearn/linear_model/_glm/tests/test_glm.py -k test_max_iter_argument -vsl
```

[Output](https://github.com/data-umbrella/data-umbrella-scikit-learn-sprint/blob/master/contributing/2021-12-12-example-failed-tests.md)

I see that 5 tests have failed:  
1. `max_iter` = `'not a number'`  
```bash
>               if n_iterations >= maxiter:
E               TypeError: '>=' not supported between instances of 'int' and 'str'
../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/lbfgsb.py:367: TypeError
```

2. `max_iter` = `0`  
```bash
>           glm.fit(X, y)
E           Failed: DID NOT RAISE <class 'ValueError'>
sklearn/linear_model/_glm/tests/test_glm.py:150: Failed
```

3. `max_iter` = `-1`
```bash
>           glm.fit(X, y)
E           Failed: DID NOT RAISE <class 'ValueError'>
sklearn/linear_model/_glm/tests/test_glm.py:150: Failed
```

4. `max_iter` = `5.5`
```bash
>           glm.fit(X, y)
E           Failed: DID NOT RAISE <class 'ValueError'>
sklearn/linear_model/_glm/tests/test_glm.py:150: Failed
```

5. `max_iter` = `[1]`
```bash
>               if n_iterations >= maxiter:
E               TypeError: '>=' not supported between instances of 'int' and 'list'
../../miniforge3/envs/sklearndev/lib/python3.9/site-packages/scipy/optimize/lbfgsb.py:367: TypeError
```

### Add parametrized tests

The tests must fail before adding validation. This is an example of how we will add a parametrized test:  
Current:  
```python  
@pytest.mark.parametrize("max_iter", ["not a number", 0, -1, 5.5, [1]])
def test_glm_max_iter_argument(max_iter):
    """Test GLM for invalid max_iter argument."""
    y = np.array([1, 2])
    X = np.array([[1], [2]])
    glm = GeneralizedLinearRegressor(max_iter=max_iter)
    with pytest.raises(ValueError, match="must be a positive integer"):
        glm.fit(X, y)
```

We will update the test as we have done below:  
```python
@pytest.mark.parametrize(
    "params, err_type, err_msg",
    [
        ({"max_iter": 0}, ValueError, "max_iter == 0, must be >= 1"),
        ({"max_iter": -1}, ValueError, "max_iter == -1, must be >= 1"),
        (
            {"max_iter": "not a number"},
            TypeError,
            "max_iter must be an instance of <class 'numbers.Integral'>, not <class"
            " 'str'>",
        ),
        (
            {"max_iter": [1]},
            TypeError,
            "max_iter must be an instance of <class 'numbers.Integral'>,"
            " not <class 'list'>",
        ),
        (
            {"max_iter": 5.5},
            TypeError,
            "max_iter must be an instance of <class 'numbers.Integral'>,"
            " not <class 'float'>",
        ),
    ],
)
def test_glm_scalar_argument(params, err_type, err_msg):
    """Test GLM for invalid max_iter argument."""
    y = np.array([1, 2])
    X = np.array([[1], [2]])
    glm = GeneralizedLinearRegressor(**params)
    with pytest.raises(err_type, match=err_msg):
        glm.fit(X, y)
```

I run the tests.  
Note: I have renamed the test function.  
```bash
pytest sklearn/linear_model/_glm/tests/test_glm.py::test_glm_scalar_argument
```

The tests fail, as expected, because invalid values are being input.  

```bash

E           ValueError: Maximum number of iteration must be a positive integer; got (max_iter=5.5)

sklearn/linear_model/_glm/glm.py:232: ValueError
==================================================== 5 failed in 0.59s =====================================================
(sklearndev) 
```
### Add and run validation

Next, in the `glm.py` file, I do two things:  
1. Import the needed function
```python
from ...utils import check_scalar
```


2. Add in the `check_scalar` function in the `def fit` function. The function here checks that for `max_iter` is:  
    - an integer
    - has a has a minimum value of `1`
    - has no maximum value
    - is within this range: `[1, )`. Note that no upper bound is specified.  

```
        check_scalar(
            self.max_iter,
            name="max_iter",
            target_type=numbers.Integral,
            min_val=1,
            max_val=None,
            include_boundaries="left",
        )
```

## Confirm tests are passing!
After doing the above, we see that all 5 tests are now passing:  

```bash
~/software-build/scikit-learn  xscalar_glm ✔                                                                                           8d  
▶ pytest sklearn/linear_model/_glm/tests/test_glm.py -k test_glm_scalar_argument -vsl

=========================================================== test session starts ============================================================
platform darwin -- Python 3.9.7, pytest-6.2.5, py-1.10.0, pluggy-1.0.0 -- /Users/reshamashaikh/miniforge3/envs/sklearndev/bin/python
cachedir: .pytest_cache
rootdir: /Users/reshamashaikh/software-build/scikit-learn, configfile: setup.cfg
plugins: cov-3.0.0
collected 78 items / 73 deselected / 5 selected                                                                                            

sklearn/linear_model/_glm/tests/test_glm.py::test_glm_scalar_argument[params0-ValueError-max_iter == 0, must be >= 1] PASSED
sklearn/linear_model/_glm/tests/test_glm.py::test_glm_scalar_argument[params1-ValueError-max_iter == -1, must be >= 1] PASSED
sklearn/linear_model/_glm/tests/test_glm.py::test_glm_scalar_argument[params2-TypeError-max_iter must be an instance of <class 'numbers.Integral'>, not <class 'str'>] PASSED
sklearn/linear_model/_glm/tests/test_glm.py::test_glm_scalar_argument[params3-TypeError-max_iter must be an instance of <class 'numbers.Integral'>, not <class 'list'>] PASSED
sklearn/linear_model/_glm/tests/test_glm.py::test_glm_scalar_argument[params4-TypeError-max_iter must be an instance of <class 'numbers.Integral'>, not <class 'float'>] PASSED

===================================================== 5 passed, 73 deselected in 0.23s =====================================================
(sklearndev) 
```

## Reminders

When submitting the pull request (PR):  
- Label PR with prefix "MAINT"
- A changelog entry is not required


---

## Resources

### Rebuild source code

If tests are failing, I may need to rebuild the source code, using below syntax:  
```bash
pip install -e . --no-build-isolation -v
```
or

```
python setup.py clean
pip install --verbose --no-build-isolation --editable .
```

### Run full test suite in sklearn
To run the full suite of tests, it takes about 20 minutes on my computer.  

```bash
pytest sklearn
```

There is example output of the tests in [2021-12-12-pytest_sklearn_output.md](https://github.com/data-umbrella/data-umbrella-scikit-learn-sprint/blob/master/contributing/2021-12-12-pytest_sklearn_output.md)

```bash
E       AssertionError: 
E         This test fails because scikit-learn has been built without OpenMP.
E         This is not recommended since some estimators will run in sequential
E         mode instead of leveraging thread-based parallelism.
E         
E         You can find instructions to build scikit-learn with OpenMP at this
E         address:
E         
E             https://scikit-learn.org/dev/developers/advanced_installation.html
E         
E         You can skip this test by setting the environment variable
E         SKLEARN_SKIP_OPENMP_TEST to any value.
E         
E       assert False
E        +  where False = _openmp_parallelism_enabled()

sklearn/tests/test_build.py:33: AssertionError
===== 1 failed, 25839 passed, 205 skipped, 250 xfailed, 62 xpassed, 2290 warnings in 1002.24s (0:16:42) ======
(sklearndev) 
~/software-build/scikit-learn  xscalar_glm ✔  

```

### Running Individual Tests
Typically, to run the full test suite, I would type `pytest sklearn`, which takes about 20 minutes.

Individual tests can be run using the syntax below, there are a couple of ways to do it: 
```bash
pytest sklearn/linear_model/_glm/tests/test_glm.py -k test_glm_max_iter_argument -vsl
```

```bash
pytest sklearn/linear_model/_glm/tests/test_glm.py::test_glm_max_iter_argument
```

This is the output observed after running the test.    
```bash
▶ pytest sklearn/linear_model/_glm/tests/test_glm.py::test_glm_max_iter_argument
=================================================== test session starts ====================================================
platform darwin -- Python 3.9.7, pytest-6.2.5, py-1.10.0, pluggy-1.0.0
rootdir: /Users/reshamashaikh/software-build/scikit-learn, configfile: setup.cfg
plugins: cov-3.0.0
collected 5 items                                                                                                          

sklearn/linear_model/_glm/tests/test_glm.py .....                                                                    [100%]

==================================================== 5 passed in 0.17s =====================================================
(sklearndev) 
~/software-build/scikit-learn  xscalar_glm ✔  
```

Because I consolidated some existing tests and added the new ones, I renamed the test. I would run the following for the test:  
```bash
pytest sklearn/linear_model/_glm/tests/test_glm.py -k test_glm_scalar_argument -vsl
```


---

## Acknowledgements
- Guillaume LeMaitre [@glemaitre](https://github.com/glemaitre)
- Julien Jerphanon [@jjerphan](https://github.com/jjerphan)
- Thomas J. Fan [@thomasjpfan](https://github.com/thomasjpfan)
- Genesis Valencia [@genvalen](https://github.com/genvalen)

---

## Part 2: `PoissonRegressor`

1. Virtual environment activated:  `conda activate sklearndev`
2. Identify class to work on:  `PoissonRegressor`
3. Working with this file: [sklearn/linear_model/glm.py](https://github.com/scikit-learn/scikit-learn/blob/efa5e3eee5dfa696cc46d462cf20bdf1c95e75cc/sklearn/linear_model/_glm/glm.py)
4. Working with associated test: [sklearn/linear_model/_glm/tests/test_glm.py](https://github.com/scikit-learn/scikit-learn/blob/efa5e3eee5dfa696cc46d462cf20bdf1c95e75cc/sklearn/linear_model/_glm/tests/test_glm.py)
5. Create working branch from `main` branch
```bash
git checkout main
git pull upstream main
git checkout -b xscalar_poissonreg
```
7. Identify scalar numerical parameters and the valid range of values for the class `PoissonRegressor`
    - `alpha`, value range: `[0.0, inf)`
    - `max_iter`, value range: `[1, inf)`
    - `tol`, value range: `(0.0, inf)`
    - `verbose`, value range: `[1, inf)`
8. Add parameter interal ranges to the docstring
    - `alpha`, Values should be in the range `[0.0, inf)`.
    - `max_iter`, Values should be in the range `[1, inf)`.
    - `tol`, Values should be in the range `(0.0, inf)`.
    - `verbose`, Values should be in the range `[1, inf)`.
9. Run tests:  `pytest sklearn/linear_model/_glm/tests/test_glm.py -k test_glm_scalar_argument -vsl`
10. There is no `def fit` for class `PoissonRegressor`   

