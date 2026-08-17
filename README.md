# Draelos Lab Website
Our website is developed using HTML and then published through Netlify. This README will guide you through how to update website pages, format images, and publish the site. 

* [Updating Pages](#updating-pages)
    * [Home](#home)
    * [People](#people) 
    * [Research](#research) 
        * [Funding](#funding)
    * [Publication](#publications)
    * [News](#news)
        * [BlueSky Tweets](#bluesky-tweets)
* [Formatting Images](#formatting-images)
* [Previewing and Publishing Site](#previewing-and-publishing)
         


<a id="updating-pages"></a>
## Updating Pages
<a id="home"></a>
### Home 
To update the homepage, navigate to the `index.html` script, where you can change the research statement and/or main image. 

<a id="people"></a>
### People
In the `_persons/` folder, create `firstname-lastname.html` file for each new member of the lab. An example script for an active member is shown below: 
```
<!-- _persons/firstname-lastname.html -->
---
name: 
role: 
photo: 
active: True
---
<span style="font-size: 17px">
    <b>M.S.:</b>  <br>
    <b>B.S.:</b>  <br><br>
    <b>Project(s):</b>
    <b>Secret skill:</b>
    <b>Email:</b> 
</span>
```
The `name` section should include their first, last, preferred name (optional), titles, and preferred pronouns. The `role` is their role in the lab: Research Scientist, Postdoc, Phd Student, MS Student, Visiting Scholar, Undergraduate (see `_data/roles.yml`). Their `photo` should be the path to their JPG or PNG file in `/img/`. The `active` status is set to either True or False. An example script for a non-active student is shown below: 
```
---
name: 
role: 
photo: 
active: False
current: Currently pursuing ...
---
```
#### Page formatting 
To change the format of the bio sections, you'll need to modify the `_includes/person.html` file. 

To change the format/layout of the whole page, you'll need to modify the `people.html` file. 

<a id="research"></a>
### Research
In the `_projects/` folder, create a `project-name.html` file to create a new project section. An example script for an active project is shown below: 
```
<!-- projects/project-name.html -->
---
title:
image: 
active: true
order: 1
---
RESEARCH BLURB...

<!-- Comment: Caption for images -->
<small><i>Figure: 
</i></small> 
```
To update an existing project, simply update the research blurb. The `title` is simply the title of the research project. The `photo` should be the path to the project's JPG or PNG file in `/img/`. The `active` status is set to either True or False. The `order` is the actual order of the projects. If you change the order of one project, you will need to subsequently change the order of the other projects. 

<a id="funding"></a>
#### Funding Section
The `funding.html` file contains a list of our current funding sources. This will need to be updated any time we receive grants or additional funding. You will also need to update the `/img/research-funding.png` image which is just a compilation of the logos of our funding soures. See [Formatting Images](#formatting-images) section for how to update images. 

#### Page formatting 
To change the format of the research projects section, you'll need to modify the `_includes/project.html` file. 

To change the format/layout of the whole page, you'll need to modify the `research.html` file. 

<a id="publications"></a>
### Publications
In the `_bibliography/` folder, there are two .bib files: `prior_references.bib` and `recent_references.bib`. To add a new publication, update the `recent_references.bib`. An example is shown below: 
```
<!-- _bibliography/recent_references.bib -->
@article{TAG_NAME,
  title = {},
  author = {},
  journal = {},
  year={}, 
  URL = {},
}
```
"TAG_NAME" is just a short descriptive name for the publication (e.g. lastnameYYYY or lastnameYY). `title` is the official title of the publication. `author` is a list of all author names in the format (First Author Last Name, First Author First Name and Second Author Last Name, Second Author First Name, ...). `journal` is the journal name of the publication. `year` is the year of publication. `URL` can either be the URL link to the journal's publication or can be a link to a PDF attachment in the `attachments/` folder. 

The bibliography is in APA format. 

#### Page formatting 
To change the format/layout of the whole page, you'll need to modify the `publications.html` file. 

<a id="news"></a>
### News
In the `_news/` folder, you can add `news_post.html` to create a new post. An example script is shown below: 
```
<!-- _news/news-post.html -->
---
title: 
date: 
image: 
image_pos: 
---

<span>
NEWS POST
</span>
```

`title` is the name of the news post. `date` is the date the event occured. `image` is the path to the JPG or PNG file in the `/img/` folder. `image_pos` is where you want to the image to fall: `left`, `right`, `center`

<a id="bluesky"></a>
#### BlueSky Tweets
In the `_bluesky/` folder, you can add a tweet.html file to link a tweet to the news page. To link a BlueSky tweet, you simply need the URI and the URL of the tweet. An example is shown below:

```
<!-- _bluesky/tweet.html -->
---
bsky_uri: ""
bsky_url: ""
---
```

#### Page formatting 
To change the format of the news posts, you'll need to modify the `_includes/news.html` file. 

To change the format/layout of the whole page, you'll need to modify the `news.html` file. 

<a id="formatting-images"></a>
## Formatting Images
For formatting images and spacing throughout the whole website, we utilize CSS. We mainly use `css/bootswatch-darkly.css` and  `css/styles.css` to modify existing margins, but you can also add new types. 

For most cases, it is easy to save square images (1:1 ratios) to the `/img/` folder. It is easier to have an edited/ready-for-viewing image saved than trying to edit/format the image using CSS. 

<a id="preview-and-publish"></a>
## Previewing and Publishing Site
### Netlify
Once you push your changes to Github, [Netlify](https://app.netlify.com/teams/draeloslab/projects) will automatically start processing the deploy. Auto publishing is turned off so that you can check the preview before publishing. See picture below for an example of Netlify's Deploy tab. 

![netfliy](/img/netlify_example.png)

## Quickstart
```
# install rbenv
# https://www.mikekasberg.com/blog/2020/09/27/set-up-a-ruby-dev-environment.html

# insall ruby according to .ruby_version
rbenv install 3.2.1

gem install jekyll bundler

bundle install

bundle exec jekyll serve --port 4001
```
