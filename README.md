# Data Umbrella Jekyll Blog

This repository houses the code for Data Umbrella's Jekyll blog hosted at [https://blog.dataumbrella.org]. The blog was scaffolded using the Menca theme. For more information about the Menca theme check it out in action [Live Demo](https://menca.netlify.app/) and the developer's Jekyll theme entry by [Artem Sheludko](https://jekyllthemes.io/developers/artem-sheludko).

### Contributing

#### Installing Ruby & Jekyll

If this is your first time using Jekyll, please follow the [Jekyll docs](https://jekyllrb.com/docs/installation/) and make sure your local environment (including Ruby) is setup correctly.

### Development

#### 1. Fork the repository

  Go to https://github.com/data-umbrella/data-umbrella.github.io/fork to fork the repository.

#### 2. Clone your fork.

  ```
  git clone https://github.com/YOUR_GITHUB_USERNAME/data-umbrella.github.io.git
  ```

#### 3. Install dependencies

  ```
  cd data-umbrella
  bundle install
  ```

#### 4. Run the development server

  ```
  bundle exec jekyll serve
  ```

#### 5. Open the app in the browser

Visit the app at [http://localhost:4000](http://localhost:4000).

#### 6. Commit code changes

```
git add .
git commit -m "My awesome code change"
git push origin -u example-user/example-branch-name
```

#### 7. Open Pull Request against upstream repository

Visit your forked repository on Github https://github.com/YOUR_GITHUB_USERNAME/data-umbrella.github.io and click the Compare and pull request button at the top of the page. Once you open a pull request a owner of the repository will review your code, approve your changes or request updates before merging.

### Deployment

This site is automated deployed to Netlify via Github Actions. See Jekyll's documentation on the  [Deployment Methods](https://jekyllrb.com/docs/deployment-methods/) for more information about deploying Jekyll apps.

### Support

For problems related to the blog site please create a [new issue](https://github.com/data-umbrella/data-umbrella.github.io/issues/new) on this Github repository.
