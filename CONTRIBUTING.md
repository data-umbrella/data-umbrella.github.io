# Contributing to the Data Umbrella Blog
This repository houses the code for Data Umbrella's **Jekyll** blog hosted at [blog.dataumbrella.org](https://blog.dataumbrella.org). The blog was scaffolded using the [Menca theme](theme-author.md) by [Artem Sheludko](https://jekyllthemes.io/developers/artem-sheludko).

- **Ruby**: is a programming language used to build software applications
- **Jekyll**: is a static site generator written in Ruby
- Ruby & Jekyll: Jekyll is built with Ruby, so to use Jekyll, you need to have Ruby installed on your system. When you run Jekyll commands (like `jekyll serve`), you're actually running Ruby scripts under the hood.

## Running the blog website locally

### Installing Ruby & Jekyll

If this is your first time using Jekyll, please follow the [Jekyll docs](https://jekyllrb.com/docs/installation/) and make sure your local environment (including Ruby) is set up correctly.

### Development

#### 1. Fork the repository

  Go to https://github.com/data-umbrella/data-umbrella.github.io/fork to fork the repository.

#### 2. Clone your fork

  ```bash
  git clone https://github.com/YOUR_GITHUB_USERNAME/data-umbrella.github.io.git
  ```

#### 3. Install dependencies

  ```
  cd data-umbrella.github.io
  bundle install
  ```

#### 4. Run the development server (run Jekyll locally)

  ```
  bundle exec jekyll serve
  ```

#### 5. Open the app in the browser

Visit the app at: [http://localhost:4000](http://localhost:4000)

#### 6. Commit code changes

```
git add .
git commit -m "My awesome code change"
git push origin -u example-user/example-branch-name
```

#### 7. Open Pull Request against upstream repository

Visit your forked repository on GitHub https://github.com/YOUR_GITHUB_USERNAME/data-umbrella.github.io and click the Compare and pull request button at the top of the page. Once you open a pull request a owner of the repository will review your code, approve your changes or request updates before merging.

### Deployment

This site is automated deployed to Netlify via GitHub Actions. See Jekyll's documentation on the  [Deployment Methods](https://jekyllrb.com/docs/deployment-methods/) for more information about deploying Jekyll apps.

### Support

For problems related to the blog site please create a [new issue](https://github.com/data-umbrella/data-umbrella.github.io/issues/new) on this GitHub repository.

---

## Contributing & Operational Guidelines


### Blog Posts
- The blog posts are in markdown file (`.md`) and are located at: [data-umbrella.github.io/_posts](https://github.com/data-umbrella/data-umbrella.github.io/tree/main/_posts)
- You can copy and rename an existing markdown post and edit it.

### Images
- Images can be placed in this folder: [data-umbrella.github.io/images](https://github.com/data-umbrella/data-umbrella.github.io/tree/main/images)
- We suggest putting images related to one blog in its own folder to keep the files organized.

Example text:  
```
![Mountains]({{site.baseurl}}/images/template_images/06-2.jpg)
*Photo by [Oleg Chursin](https://unsplash.com/photos/vaPoJZB9Mzg) on [Unsplash](https://unsplash.com/)*
```


### Syntax Examples

#### Example of highlighting

```html
<span style="background-color: #FFFFC5;">
working sessions to contribute to the open source library.            
</span>
```

### Adding timestamps to Blog

1) Copy the timestamps from the video into a Google doc
2) Download the Google doc as a markdown file
3) Upload the markdown file to the GitHub repo
4) Copy the timestamps in markdown format into the markdown file you are working with in VSC


#### Example of adjusting image sizes

```html
### Sessions 1 & 2
<p float="left">
   <a href=""> </a>
  <img src="../images/2022-2023-pymc-study-sessions/S01-pymc.png" width="45%" height="45%" style="padding:1px;border:thick solid black;" align="top" />
   <a href=""></a>
  <img src="../images/2022-2023-pymc-study-sessions/S02-pymc.png" width="45%" height="45%" style="padding:1px;border:thick solid black;" align="top"/> 
</p>
```

### all-contributors bot
- [Instructions](https://github.com/data-umbrella/.github/blob/main/CONTRIBUTING.md) for using the `all-contributors` bot
- [Open issue to add contributors](https://github.com/data-umbrella/data-umbrella.github.io/issues/127)

## Questions
Any questions, please open up an [issue](https://github.com/data-umbrella/data-umbrella.github.io/issues). 

## Thank you
Thank you for contributing.


