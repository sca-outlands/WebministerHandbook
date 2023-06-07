This is a DRAFT version of the Society for Creative Anachronism's Webminister Handbook. This document is owned by the Society Webminister. It is hosted here for the purpose of editing and updating, under specific permission to do so.

# Editing

To edit a chapter, go to the relevant file in `handbook` and hit the "Edit" button. Once you commit a change, it should show up a few minutes later at https://sca-soc-web.gitlab.io/

# Managing releases

Revisions to the handbook aren't official until a new editio of the handbook has been approved.
To manage a release, use this prpocess:

- branch `main` is the current, approved release
- branch `draft` is the next version to go for approval
- when a draft is approved, update the date/version info and merge it into main
- then remove the date/version info again in `draft`, ready for the next round

# Markdown

See [John Gruber's Introduction to Markdown](https://daringfireball.net/projects/markdown/basics) for more examples.

## Lists

The chapters and appendices are written in Markdown. The first few lines are bounded by `---` and between is some metadata about the item in the collection (e.g. `title:`) which is used by the code that builds the book. This metadata is called "front matter". Then below the second `---` is the content of the chapter.

```
You can make unordered lists:
* item 1
* item 2

Ordered lists:
1. item 1
2. item 2
2. item 3
2. (the numbers don't need to increase)
```

You can make unordered lists:
* item 1
* item 2

Ordered lists:
1. item 1
2. item 2
2. item 3
2. (the numbers don't need to increase)

## Links

```
[text for the link](http://www.google.com)
```

[text for the link](http://www.google.com)

## Code

```
    4 spaces indented
    will show code <html> for instance
```

    4 spaces indented
    will show code <html> for instance

## Emphasis

```
**double will bold**

*single will italicise* 
```

**double will bold**

*single will italicise*

## Headers


```
# h1

## h2

### h3

#### h4

You can also use a line of equals signs for h1
==============================================

and a line of dashes for h2
---------------------------
```

# h1

## h2

### h3

#### h4

You can also use a line of equals signs for h1
==============================================

and a line of dashes for h2
---------------------------

# Running and editing locally

If you would like to build the document on your home machine, run Jekyll inside of Docker:

- Install [Docker Desktop](https://www.docker.com/products/docker-desktop) (or for Linux, install [Docker](https://docs.docker.com/engine/install/) and [Docker Compose](https://docs.docker.com/compose/install/))
- Clone this repository
- In the top level directory of the repository, run `docker-compose up`
- Visit `https://localhost:4000/`
- To get a shell inside the docker container, instead run `docker-compose run --service-ports jekyll ash`

To add a chapter, place it inside `_handbook`. Note that the two lines of triple-dashes at the top of the file are essential. Any metadata for the chapter can be placed here (e.g. `title`) and this metadata can be accessed when the page is built (e.g. `{{ chapter.title }}`).

For more information about the tool that builds the site, visit [the Jekyll website](https://jekyllrb.com/docs/).