# Introduction

Welcome to the wiki!

### How to edit a page

To edit a page, just find it in the github repository and edit from there, or pull the repostiory and edit it on your PC. Then push to master and the action script should push it to the pages website. Don't push to the gh-pages repo as this is the backend for rendering the website etc. 

### How to create a new page

Add the page to the necessary place in the github repository. Then, add it to the [SUMMARY.md](summary.md) file as a member of a nested list in the correct section, and link the page name to the page itself using the following syntax: 

```markdown
* [section name](path/to/section.md)
  *[page name](path/to/page.md)
```

### How to create a new section 

To create a new section, do the same as you would do to add a new page, but when adding it to the [SUMMARY.md](summary.md) file, put it as a top level element in the list: 

```markdown
* [new section](path/to/section.md)
