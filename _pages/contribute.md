---
title: Contribute
layout: default
nav_order: 100
---

# Contributing to the Website
You are encouraged to contribute to the website documentation by editing existing pages, or creating new pages (e.g., guides). Instructions for how to do this are given below.

## Website Architecture
The website is written with [Jekyll](https://jekyllrb.com/) using the [Just-the-Docs](https://just-the-docs.github.io/just-the-docs/) template and freely hosted with [Github Pages](https://pages.github.com/). Jekyll allows you to create a website with simple markdown, with navigation and styling being handled automatically by your chosen template.

The public Github repository for the website can be found [here](https://github.com/IGB190/igb190.github.io). The pages are automatically generated from the content of the repository.

## Making Changes via Pull Requests
Updates to the site are handled via Pull Requests (PRs). PRs are an industry standard way of updating repositories in a safe and standardised way. To create a pull reuest, do the following:

1. Fork the repository by going to the [repository page](https://github.com/IGB190/igb190.github.io) and pressing the 'Fork' button in the top-right.
1. Give the forked repository a name, and then press the `Create Fork` button.
1. Clone the forked repository to your machine.
1. Create a new branch for the changes you are making.
1. Make any changes you would like to add to the site.
1. Commit the changes and push them to the forked repository.
1. Go to the forked repository on Github (the one you just pushed to). Select the 'Pull requests' tab, then click the 'New pull request' button.
1. On the left, select the main repository and the `main` branch. On the right, select the forked repository and the branch that has all of the changes you made.
1. Add a title and brief description describing the changes.
1. Click the "Create pull request" button to submit it for review.
1. Wait for the pull request to be accepted (or for a response to be given).

## Adding or Updating Pages
The content for the website can be found in the `_pages` directory. All markdown files in this folder are automatically converted into website pages with correct navigation. For example, you can see the markdown that was used to generate this page [here](https://github.com/IGB190/igb190.github.io/_pages/contribute.md).

The [template](https://just-the-docs.github.io/just-the-docs/) page for the Just-the-Docs template has examples for all valid markdown you can use (e.g., callout boxes, code snippets, table of contents).

Images should be uploaded to the `_pages\assets` folder.


