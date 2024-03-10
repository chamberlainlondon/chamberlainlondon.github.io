---
title: 'How to Build a Unique Student Website and Why You Should (Using AcademicPages, a fork of Minimal Mistakes)'
date: 2024-03-11
permalink: /posts/2024/03/build-student-website/
collection: posts
toc: true
excerpt: read_time
header:
  overlay_image: https://chamberlainlondon.github.io/images/posts/2024-03-01-build-student-website/code.jpg
  overlay_filter: rgba(0, 0, 0, 0.5)
  caption: "Photo credit: [**Wikimedia Commons**](https://commons.wikimedia.org/wiki/File:Programming_code.jpg)"
tags:
  - web development
---

It is easier than ever to create a student website using services like [google sites](https://sites.google.com/new?tgif=d), [squarespace](https://www.squarespace.com/), and [wix](https://www.wix.com/). However, building a site using one of these platforms can often feel repetetive and uninspiring, as countless other users are following the same templates to generate sites. 

If you're interested in creating a more unique student site you can tinker with and control more of, I'll teach you how to create a site like [this one](https://londonchamberlain.com/) with little coding experience:

# Why Build a Student Website?

Creating a personal website can be a game-changer for students. Your student site can be a dynamic platform to showcase achievements, skills, and passions. It's not just about impressing others; it's about crafting an online identity that sets you apart in a competitive world. 

Through your website, you can paint a vivid picture of who you are, what you've accomplished, and where you're headed, leaving a lasting impression on users. Plus, building and maintaining a website isn't just about the end product; it's a learning journey that hones valuable digital skills like web design, coding, and [SEO](https://en.wikipedia.org/wiki/Search_engine_optimization)—skills that are increasingly useful today. Your website isn't just a one-time project--it's a long-term investment in yourself.

Let's learn how to create one together!

# How to Build a Student Site

Now that you know why you should build a site of your own, how can we actually do it? Although there are many approaches a user can take to launch their own student site, this guide is going to focus on developing an [AcademicPages](https://academicpages.github.io/) static site using Github to store and deploy the code, and [Porkbun](https://porkbun.com/) (optional) to attach your unique domain name.

## Using GitHub

If you don't already have a GitHub account, no worries. It's easy to sign up.

1. First, Navigate to [GitHub](https://github.com/).
2. Enter your email address and click "Sign up for GitHub."
3. Follow the prompts to create your personal account.

During sign up, you'll be asked to verify your email address. Without a verified email address, you won't be able to complete some basic GitHub tasks, such as creating a repository.

If you're having problems verifying your email address, there are some troubleshooting steps you can take. For more information, see "[Verifying your email address](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/verifying-your-email-address#troubleshooting-email-verification)."

### Forking Repositories

Once we're signed up for GitHub, we'll want to fork a respository. The site we'll be creating in this tutorial uses the repository, Academic Pages, as the foundation for our site. We'll fork this to get started. 

If you've never forked a repository before, don't worry. We'll walk through how to fork the Academic Pages repository below:

1. On GitHub.com, navigate to the [academicpages/academicpages.github.io](https://github.com/academicpages/academicpages.github.io) repository.

2. In the top-right corner of the page, click Fork.

<br>

![Screenshot of the main page of repository. A button, labeled with a fork icon and "Fork 59.3k," is outlined in dark orange.](https://chamberlainlondon.github.io/images/posts/2024-03-01-build-student-website/fork.png)

<br>

3. Under "Owner," select the dropdown menu and click an owner for the forked repository.

4. By default, forks are named the same as their upstream repositories. Optionally, to further distinguish your fork, in the "Repository name" field, type a name.

5. Optionally, in the "Description" field, type a description of your fork.

6. Optionally, select Copy the DEFAULT branch only.

For many forking scenarios, such as contributing to open-source projects, you only need to copy the default branch. If you do not select this option, all branches will be copied into the new fork.

7. Click Create fork.

### Accessing Repository via Local Computer (optional)

#### Syncing Cloned Repository to GitHub (optional)

Once your site is forked to your very own repository, you'll want to deploy it for the world to see! Don't worry, you can come back after to make more changes.

### Deploying Site

To check your site out on the web, we'll lastly need to deploy it. To deploy:

1. Under your repository name, click **Settings**. If you cannot see the "Settings" tab, select the **...** dropdown menu, then click **Settings**.

2. In the "Code and automation" section of the sidebar, click **Pages**.

3. Under "Build and deployment", under "Source", select **Deploy from a branch**.

4. Under "Build and deployment", use the branch dropdown menu and select a publishing source. I publish from the main branch.

<br>

![Screenshot of the pages page of the settings tab. A button, labeled with "None" and a carrot icon is outlined in dark orange.](https://chamberlainlondon.github.io/images/posts/2024-03-01-build-student-website/branch.png)

<br>

5. Optionally, use the folder dropdown menu to select a folder for your publishing source. I use /(root).

Due to regular Jekyll theme updates, your AcademicPages fork of Minimal Mistakes may not deploy the first time you try[^1]. If this is the case, head over to the [issues]() tab of the AcademicPages repository and read the solutions provided.
{: .notice--danger}

# How to Customize your Site

Now that we've got a working site, we'll want to make some changes. To begin, play around with the **_config.yml** variables in your files. Many of your variables can be updated in the **# Site Settings** and **# Site Author** sections, like follows:

```markdown
# Site Settings
locale                   : "en-US"
title                    : "Home"
title_separator          : "-"
name                     : &name "London Chamberlain"
description              : &description "personal description"
url                      : https://www.londonchamberlain.com # the base hostname & protocol for your site e.g. "https://mmistakes.github.io"
baseurl                  : "" # the subpath of your site, e.g. "/blog"
repository               : "chamberlainlondon/chamberlainlondon.github.io"
```

```markdown
# Site Author
author:
  name             : "London Chamberlain"
  avatar           : "London_Headshot_Greyscale_Background.png"
  bio              : "Economics @ The University of Texas at Austin"
  location         : "Austin, TX"
  employer         : 
  pubmed           : # example: "https://www.ncbi.nlm.nih.gov/pubmed/?term=john+snow"
  googlescholar    : # example: "http://yourfullgooglescholarurl.com"
  email            : "london.chamberlain@utexas.edu"
  researchgate     :  # example: "https://www.researchgate.net/profile/yourprofile"
  uri              :
  bitbucket        :
  codepen          :
  dribbble         :
  flickr           :
  facebook         :
  foursquare       :
  github           : "chamberlainlondon"
  google_plus      :
  keybase          :
  instagram        :
  impactstory      : #"https://profiles.impactstory.org/u/xxxx-xxxx-xxxx-xxxx"
  lastfm           :
  linkedin         : "londonchamberlain"
  medium           : 
  orcid            : "http://orcid.org/0009-0008-6432-8474"
  pinterest        :
  soundcloud       :
  stackoverflow    : # http://stackoverflow.com/users/123456/username
  steam            :
  tumblr           :
  twitter          : # example: "replacethistwitterhandle"
  upwork           : 
  vine             :
  weibo            :
  xing             :
  youtube          :
  wikipedia        :
```

## Local Changes

Tip: Make small changes one-by-one and test the effects. Making multiple commits and alterations often ends up with unexpected results where developers don't know where the issues lie.
{: .notice--warning}

## Pushing to Web

## Using Custom Web Domain

Using a custom web domain when 

### Purchasing a Domain

### Connecting Domain to Static Site

## Moving Forward & Resources

Check out my next post that delves into how to customize your site to your liking: link

If you'd like to alter your site in a way I haven't covered, check out the issues page of the Academic Pages repository, linked [here](https://github.com/academicpages/academicpages.github.io/issues?q=is%3Aissue). Other users like yourself have 

### Resources

<details>
  <summary><b>Static Sites That Inspire Me</b><br>
  <i>Check out the code behind these sites if you like a particular feature!</i>
</summary>
  <br>
  <p>
    <ul>
      <li>Check out Giulio Schinaia's <a href="https://gschinaia.github.io/">academic site</a>. I especially like Giulio's use of the light/dark toggle button.</li>
      <li>Rob Williams' <a href="https://jayrobwilliams.com/">academic site</a> boasts a wealth of static site knowledge for you to dig through. I've implemented so many aspects of Rob's site in my own using his commit history, as well as his posts. Rob's own <a href="https://jayrobwilliams.com/posts/2020/06/academic-website/">post</a> about creating an academic site was the inspiration for this post. Sorry for the theft, Rob.</li>
      <li>Antoine Soetewey's <a href="https://www.socialscienceregistry.org/trials/4740">personal site</a> is elite. His R blog and use of an English/French language toggle are both super fascinating to check out.</li>
    </ul>
</p>
</details>
<br>

[^1]: Although errors change as the Jekyll theme changes, [this](https://github.com/academicpages/academicpages.github.io/issues/1902#issuecomment-1943783816) solution fixed my deploy error when I first deployed my site.
