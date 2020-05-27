# Introduction

Welcome to the [wiki](https://mlvqc.github.io/wiki)!

### How to edit a page

To edit a page, just find it in the [github repository](https://github.com/mlvqc/wiki) and edit from there, or pull the repository and edit it on your PC. Then push to master:

```markdown 
git push -u origin master
```

and the action script should push it to the pages website. Don't push to the gh-pages repo as this is the backend for rendering the website etc. 

### How to create a new page

Add the page to the necessary place in the github repository. Then, add it to the [SUMMARY.md](SUMMARY.md) file as a member of a nested list in the correct section, and link the page name to the page itself using the following syntax: 

```markdown
* [section name](path/to/section.md)
  *[page name](path/to/page.md)
```

### How to create a new section 

To create a new section, do the same as you would do to add a new page, but when adding it to the [SUMMARY.md](SUMMARY.md) file, put it as a top level element in the list: 

```markdown
* [new section name](path/to/section.md)
```
