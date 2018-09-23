---
layout: post
title: How To Set Up Your Personal Page And Blog With GitHub
---

## How To:

##### Step 1 (personal GitHub Page).
* Create a new repo in the GitHub application.
* Move website files to the repo. Home page HTML file name : index.html
   * There are a lot of websites to get nice templates. I used [html5up](https://html5up.net/).
   * Customize the template.
	```
	create local project folder
	git init
	git add (to add new website to the repo)
	git commit -m "description of commit"
	create repo on GitHub:
		name format: **username.github.io**
	add your remote repo to the local repo:
		git remote add origin repo_URL
	```
* Google Analytics:
	* See instructions [here](https://support.google.com/analytics/answer/1008015?hl=en).
* Push your repo (git push origin master).
<!--read more-->
##### Step 2 (set up blog with Poole)
1. Poole [page](https://github.com/poole/poole)
2. Any repo with index.html page can be converted into project page.
3. Blog will be available at https://_username_.github.io/_blog_name_/ where _blog_name_ is project name.

###### Add project page
* create repo with name _blog_name_ (choose any name you like) on github website
* clone your repo and add poole code
* push files
* By default you are on master branch. Create remote branch gh-pages

	```
	git checkout -b gh-pages
	git push -u origin gh-pages
	```
* Set gh-pages branch as default on git hub: [see here](https://help.github.com/articles/setting-the-default-branch/)
* delete master branch
	```
 	git branch -d master
	git push origin --delete master
	```
* Go to Settings tab in remote repository(Github website)
* In Github Pages panel there should be "Your site is ready to be published at <username.github.io/repository_name>"

###### Set Up Poole
1. Poole is based on Jekyll. To test changes locally

	```
	Install Jekyll: gem install jekyll
	Run Jekyll: jekyll serve
	```
2. Pay attention: while running Jekyll creates _site folder. It's a dynamic folder and is all the time overwritten by Jekyll
Do not make any customizations in it

* Link you project page to your personal page(edit _config.yml)

	```
	# Setup
	title:               Blog Title Here
	tagline:             ''
	home:                https://_username_.github.io
	url:                 https://username.github.io/_blog_name_
	paginate:            5
	baseurl:             /_blog_

	```

About configuration option see [here](https://jekyllrb.com/docs/configuration/options/) and about pagination see [here](https://jekyllrb.com/docs/pagination/)

