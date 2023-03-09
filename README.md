# How to host a resume on GitHub Pages and creat Static Websites
---
This readme shows how to create a static website and host it to GitHub pages by Jekyll

## Purpose:
---
1. Guide the reader how to create a Static website with resume included by using Jekyll, and host static websit on github pages.
2. Explaining how do the steps correspond to Andrew Etter's book _Modern Technical Writing_

## Content:
---
- [Prerequisites](#prerequisites)
- [Instructions](#instructions)
- [Steps relate to general principles of current Technical Writing](#steps-relate-to-general-principles-of-current-technical-writing)
- [More Resources](#more-resources)
- [Authors and Acknowledgments](#authors-and-acknowledgments)
- [FAQs](#faqs)

# Prerequisites:
---
 1. A resume formatted in Markdown  
If you don't know how to format resume by using Markdown. you can see Markdown in [More Resources](#more-resources)

 2. All tools and software used in this guide 
    - [GitHub Account](https://github.com/join)
    - [Git](https://git-scm.com/downloads)
    - [Jekyll](https://jekyllrb.com/docs/installation/)
    - [RubyInstaller (Jekyll in windows)](https://jekyllrb.com/docs/installation/windows/)

# Instructions:
---
This is the resume page I created through the following steps.
![My resume page](jiazhentian-resume.gif)

#### **Step 1:** Create a new repository
1. Click on the `+` on the main page and select new repository.
2. Make basic settings
    - Enter the repository name
    - Set Public (that Anyone can see this repository)
    - Don't Select `Add a README file`
    - Click Create repository
3. Okay we have repository now, but don't close it yet, we'll need it later

#### **Step 2:** Create, Edit, View a Static website
1. **Create**
  - Open terminal Go to the directory where you can easily find

```
cd path-to-your-directory
```
   - Run the following commands（You can replace it with the name you want to change）to Create a Static Site

``` 
jekyll new NAME
```

2. **Edit**  
Since we are using the default template in this guide, we have to make some changes in resume.  
If you want to know more about jekyll please see [More Resources](#more-resources).
 - Open `resume.md` And add the following default settings at the beginning of the resume  
   (Date, and time modified according to your own)  
   (This is done to keep your resume in the same style on default static sites)

```
---
layout: post
title:  "resume"
date:   YYYY-MM-DD 00:00:00 -0600
categories: jekyll update
---
```
- Save the file name as YYYY-MM-DD-NAME (The date, time and filename here are also up to you)
- Then move the resume files to the `_posts` folder (This folder is in the static site folder that was just created)

3. **View**
- open the terminal to go to the static website folder we created
- Run the following commands

```
bundle exec jekyii serve
```
- Then you will get the website address, open your browser and enter the website address so that we can see what the website looks like
- Click on resume and you will see the resume

4. At the end of this step we have created the static site and hosted the resume on the static site.
#### **Step 3:** Hosting on Github Pages

- open `_config.yml`
- Add your repository name to the "" after `baseurl` and save
- open the terminal to go to the static website folder we created
- Run the following commands
1. this is goona initalize this repository as like a git repository

```
git init
```
2. We need to check out the gh-pages branch so run

```
git checkout -b gh-pages
```
3. The following need to check our files
```
git status
```
4. go to commit all files to repository

```
git add .
```
```
git commit -m "initial commit"
```
5. The last thing is to put the local github repository wiht the github this is goona initalize this repository as like a git repository
- Copy the link that show on our repository on GitHub, and run the following commands(Replace the link in the following command)
```
git remote add origin {link}
```
```
git branch -M main
```
```
git push -u origin main
```
- Now we can find our files on github

6. Click our repository's `setting` and find `page`
7. Select `main` and `root` in the `branch` and save, then wait for a while and we will get the link to the GitHub page, so we will successfully create a static website with a resume and host the website on the GitHub page.







# Steps relate to general principles of current Technical Writing:
---
1. **Use Distributed Version Control**. Firstly, We chose GitHub to host our resume because github is built on top of git, which is a distributed version control system. According to Etter's book, distributed systems have better performance, support offline work, and have the advantage of multiple people working on the same file. So it is very convenient to update the resume file, just upload the modified file and you can see the modified file on the static website immediately. The resume page will be kept in sync with the resume file.

2. **Use Lightweight Markup**. Second, we used markdown, a lightweight language described in the book. Markdown is a very simple lightweight language that users can master in a short time, and according to the Etter's book, writing XML by hand is crazy, lightweight is to make it easier to produce well-formed XML, and we need XML in order to build websites. So we chose to use markdown to format the resume, which makes it very easy to update it. In our example, I can update the resume page directly by modifying the resume file on GitHub

3. **Make Static Websites**.  Finally, according to the Etter's book, static sites are high-speed, simplicity, and portability,I can host static websites anywhere like GitHub pages, You can test static websites on your local computer without installing. In this guide, we've taken a static website and tested it locally, which is very easy and convenient. And our changes are also shown in real time.

# More Resources:
---
1. [Markdown tutorial](https://www.markdowntutorial.com/)
2. [Andrew Etter's book](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
3. [Mike Dane's Jekyll tutorial](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB)
# Authors and Acknowledgments:
---
- Andrew Etter
- Mike Dane(**Jekyll tutorial**)
- Group members
  - Bradley Cook 
  - Edmund Wong 
  - KUSHAAN KASHYAP 

# FAQs
---
**Q:** Why does my page look messy?And it doesn't connect to resume correctly?  
**A:** Because the baseurl is not save correctly in the `_config.yml` file. And You did not rename the resume. Additional information: Since we are using the default theme, we need to modify the files if we want a uniform style.

**Q:** Why is Markdown better than a word processor?  
**A:** Because markdown is lightweight. We can even use it in the editor of the web without installing any software.Secondly markdomarkdowny is compatible with any operating system and has no formatting problems.  

**Q:** How to change the theme?  
**A:** We need to change the `_config.yml` to choose theme. And we can use [Jekyll theme hosted on Github](https://pages.github.com/themes/),  `remote_theme: THEME-NAME`, Replace theme-name with the name of the theme of your choice. More details can see [Basic theme tutorials ](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)