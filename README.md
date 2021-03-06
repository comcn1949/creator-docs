# Cocos Creator User Manual

## Requirements

This documentation site is powered by [GitBook](https://www.gitbook.com/). You can check out the online version [here](http://docs.cocos.com/creator/manual).

You need [Node.js](https://nodejs.org/en/) and npm to be able to build the site.

To install gitbook:

```bash
npm install gitbook-cli -g
```

Install gitbook plugins:

```bash
gitbook install
```

Install gulp and other modules:

```bash
npm install gulp -g
npm install
```

## Preview

To preview the doc, run the following command:

```bash
npm run preview
```

This will build and launch web server to host the site. It will also enable livereload plugin so your changes to the markdown source file will automatically triggers rebuild of the docs.

After generation finished, don't quit server process, run the following command in other terminal context:

```bash
gulp prune-left-bar
```

This will remove unused links from left bar.

There is also a quick method can let you preview your modification immediately:

```bash
gulp quick-preview -o file1,file2...
```
Please change the file1,file2... to your own file name, then excute preview command.
This command will help you rebuild the .bookignore file which can let you ignore the files that you didn't change when you rebuild the doc.

## Build

If you just want to build the markdown to html, use this command:

```bash
npm run build
```

You can also build the doc for ebook formats (PDF, ePub, mobi), please following this guide:

https://toolchain.gitbook.com/ebook.html

If you need to publish to the website, you'd better build it on Mac. If use Windows, some redundant .md file will also generated.

## Content Editing

The markdown source of this book is in language specific folders [/en](en) and [/zh](zh). Language options are registered in [LANGS.md](LANGS.md) file.

### Index

In each language folder there is an [SUMMARY.md](en/SUMMARY.md) file, which contains all the pages to build and also this file serves as a sidebar navigation list. Any markdown source file that are not listed in this index will not be build.

In this index file, just write links to each markdown file in a list. Indented list is for chapters that contains expandable subs. For example:

```md
- [Using Editor](getting-started/basics/editor-overview.md)
	- [Assets](getting-started/basics/editor-panels/assets.md)
	- [Scene](getting-started/basics/editor-panels/scene.md)
	- [Node Tree](getting-started/basics/editor-panels/node-tree.md)
```

Will create a toggleable chapter title `Using Editor`. Once clicked all its subs will show up.

### Front page

[index.md](en/index.md) at each language folder is the front page of the doc.

### Page content

To change the content of each page, just edit the markdown source files. There's no specific front matter format, just make sure each page has a `h1` as the title.

### Customize Style and Template

To customize styles, modify [zh/styles/website.css](zh/styles/website.css) and [en/styles/website.css](en/styles/website.css).

To change HTML templates, change the content in [zh/_layouts](zh/_layouts) and [en/_layouts](en/_layouts). Check out [Templating Guide](https://toolchain.gitbook.com/templating/) for gitbook.

## Contribution

If you encounters any typo or content problem please report issue in this repo. Pull requests are welcome!

### Style Guide for Chinese documents

[中文文档书写规范](zh/CONTRIBUTING.md)
