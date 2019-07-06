---
title: 'How to setup your Workflow using Gulp v4.0.0'
published: true
---

The best way to automate the tedious tasks.

![](https://cdn-images-1.medium.com/max/600/1*FH12a2fX61aHOn39pff9vA.jpeg)

Before writing this blog post, I was using the old way to create and maintain my front-end projects: I mostly wrote the plain CSS. I caught myself doing some tasks by hand like minifying, beautifying, prefixing and linting. This insight gave me a reason to optimize my front-end workflow to produce better code.

## **What is Gulp?**

[Gulp](https://gulpjs.com/) is a toolkit for automating painful or time-consuming tasks in your development workflow, so you can stop wasting time and focus on build something.

Gulp is built on [Node.js](https://nodejs.org/en/)/JavaScript, and the Gulp file used to give it commands must also be written in JavaScript.

* **Automation** — gulp is a toolkit that helps you automate painful or time-consuming tasks in your development workflow.

* **Platform-agnostic** — Integrations are built into all major IDEs and people are using gulp with PHP, .NET, Node.js, Java, and other platforms.

* **Strong Ecosystem** — Use npm modules to do anything you want + over 2000 curated plugins for streaming file transformations.

* **Simple** — By providing only a minimal API surface, gulp is easy to learn and simple to use.

![](https://cdn-images-1.medium.com/max/2000/1*YaOQesd0MrCKXmNZNGhwhA.png)

You can install Gulp through [NPM](https://www.npmjs.com/), and the [Github](https://github.com/gulpjs/gulp/blob/master/docs/getting-started/1-quick-start.md) repository offers a getting started guide.

## What is Sass?

Sass is the most mature, stable, and powerful professional grade CSS extension language in the world. It is also a perfect candidate to utilize our Gulp workflow.
[**Learn Sass - Best Sass Tutorials (2019) | gitconnected**
*The top 9 Sass tutorials. Courses are submitted and voted on by developers, enabling you find the best Sass lessons and…*gitconnected.com](https://gitconnected.com/learn/sass)

Don’t be confused by the SASS and SCSS options. This was a problem for me initially — .scss is Sassy CSS and is the next generation of .sass.

Sass has two syntaxes. The most commonly used syntax is known as “SCSS” (“Sassy CSS”), and is a superset of CSS3’s syntax. This means that every valid CSS3 stylesheet is valid SCSS as well. SCSS files use the extension .scss.

The second, older syntax is known as the indented syntax (or just “.sass”). Inspired by Haml’s terseness, it’s intended for people who prefer conciseness over similarity to CSS. Instead of brackets and semicolons, it uses the indentation of lines to specify blocks. Files in the indented syntax use the extension .sass.


## How did I improve my workflow?

After I installed Gulp I went to the [Gulp plugin registry](http://gulpjs.com/plugins/), searched through the 3694+ plugins and picked the ones that could benefit my workflow. I decided to make use of sass and the browser sync which was very beneficial.

The first step is to create a package.json file by typing the command

    $ npm init

Then add the details — an example is shown below:

<script src="https://gist.github.com/Jatin-8898/aa0845e635d0fd921bfafc5837ae406e.js"></script>

Now to install the necessary dependencies enter the following command.

    $ npm install --*save-dev gulp-postcss autoprefixer cssnano gulp-sourcemaps gulp browser-sync gulp-sass*

We had defined start as “gulp” in the package.json since we want to run the command of gulp on npm start.

Now create a gulp.js file at the root of the project. This file is where we write the commands to utilize Gulp

<script src="https://gist.github.com/Jatin-8898/6b36b52b1944b19e390e34f4c2a6fb9c.js"></script>

Since we don’t want to use the *var* again and again, we comma separate the variable declarations.

Now let's create the path for the source and the destination inside the same file.

<script src="https://gist.github.com/Jatin-8898/067354001ee20a1cd13142fa803e1653.js"></script>

We create our function style(). This function will pipe (pass the content through) the different transformations from the initial Sass code ultimately creating cross-browser compatible, minified CSS.

<script src="https://gist.github.com/Jatin-8898/de357b077135df3bc69d7204a64dd4d9.js"></script>

Let's create a *watcher* function which watches our Scss files and then automatically reloads with the changes using the *Browser Sync* which calls the reload function and displays our updates on the UI.

<script src="https://gist.github.com/Jatin-8898/b217d765e6d1da16b7d765acb2c7f749.js"></script>

Now add the gulp task which will run in parallel i.e keep track of the style function and the watcher in parallel.

<script src="https://gist.github.com/Jatin-8898/68db3d6a0f92eaac1528570a58132e9d.js"></script>

*Our final gulpfile.js looks like this*. 😃

<script src="https://gist.github.com/Jatin-8898/1d3162cac8e39479244c6cf7a19cfafd.js"></script>

The sample directory structure looks like this.

![Directory structure](https://cdn-images-1.medium.com/max/2000/1*7YUVSPp_J1RahOfpzvzJjA.png)

## Congratulations 🎉🎉

The gulp task has been successfully created. 😄 Now any changes made in the style.scss will automatically convert it into style.css and place it in the src/css folder.

You also do not need to refresh the page, since we have used Browser Sync.

If you really liked the article, please give this article a clap 👏 👏👏

You can star it or contribute to this repository [here](https://github.com/Jatin-8898/sass-starter-pack)
[**Jatin-8898/sass-starter-pack**](https://github.com/Jatin-8898/sass-starter-pack)
