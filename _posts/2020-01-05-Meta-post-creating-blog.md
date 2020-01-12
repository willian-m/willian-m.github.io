---
layout: post
title:  "Meta post: Creating this blog"
date:   2020-01-05 15:02:13 -0300
categories: meta blog 
---
# Creating your website using github pages

This is a meta-post. It describes how I created this blog. I may update this routinely to reflect
improvements I do on it.

## 1. Requirements

What you will need
1. GitHub account
2. A Linux development environment. It can be replaced by WSL. In fact, I am actually
   writing this from WSL.

The GitHub account is because we will be using the GitHub pages feature to host it for free. 
Furthermore, it is easy to configure and upload content, since the upload is done by just
pushing a markdown text file in a git repository.

The Linux development environment is for previewing the blog locally. GitHub pages uses Jekyll, a tool to
generate static websites. We will install and run Jekyll locally for previewing the page. However if you
desire to simply write the text locally and everything else on the web, it is also possible.

I also recommend the use of Visual Studio code for editing code and your posts. Its main advantage is the
easy integration with Windows WSL, some nice plugins for editing code and to perform spell-checking as well as
an integrated terminal. Even if you are using Linux or a Mac, VS code is available in these platforms and 
you will find plugins that will help you, thus the recommendation stands. Of course, your editing tool is a
matter of taste and you may use any other editor.

I must acknowledge that many of the instructions were retrieved from [this](https://medium.com/20percentwork/creating-your-blog-for-free-using-jekyll-github-pages-dba37272730a) post. 

## 2. Setup

For you to be able to preview your blog locally, without the need to publish it, you will need Jekyll
installed in your computer. To do so

1. From your terminal, install ruby: `sudo pacman -Syu ruby`
2. Now, you can install Jekyll itself using ruby package manager "gem": `gem install jekyll bundler`
   * This step install Jekyll into your home folder. If you do not desire this, you may try installing as a super user.
   * If you do not install Jekyll as a super user, then add the installation path to your `PATH` variable, e.g. by adding the following to your `.profile` or `.bashrc` (or whatever file your shell executes when it opens a terminal): `export PATH=$HOME/.gem/ruby/2.6.0/bin:$PATH`
3. Test if everything is working with `jekyll -v`.

Now, you are ready to create the folder where you will work. Since we will be using github-pages, I
recommend using the formula `<githubusername>.github.io` to name your folder. This is the mandatory 
name GitHub gives to the repository which will be hosting your blog and will also be the url you will
use to access it.

4. Initialize your folder with `jekyll new <githubusername>.github.io`
   *  In my case, it asked for super user password. This should not be necessary. In my case, the reason
      was that the `Gem Home` variable was set to a root-owned folder. You can check if this is your 
      case by running `bundle env`. I solved this by setting the variable `$GEM_HOME` to `$HOME/.gems` 
      with `export GEM_HOME=$HOME/.gem`. Then, just erases the folder created by the failed attempt and try
      again.
5. Before continuing, test if everything is working ny running the server: `bundle exec jekyll serve`
   *  Then, open your browser at [localhost:4000](http://localhost:4000) to see your empty blog.

Now, we configure the site to be compatible with GitHub pages.

6. Open the file named `Gemfile` and comment the line which contains `gem "jekyll"` and uncomment
   the line with `gem "github-pages"`
7. Run in your terminal the command `bundle update`

## 3. Theme and content

The main advantage of the current approach is that one is able to personalize your blog with themes developed by third-parties, allowing you to focus on the content. GitHub has some themes suggestions, but
if you research on google, you will find a plethora of themes across the web. Most of them are taylor-made
to an specific purpose (project site, FAQ page, personal portfolio etc). Pick one that pleases you. 
A suggestion of site with plenty of themes are the [http://jekyllthemes.org/](http://jekyllthemes.org/).
For instance, there I found [the theme currently being used on this blog](https://github.com/thelehhman/plainwhite-jekyll).
The project page contains instructions on how to use. But I will document here for future reference.

1. In the `_config.yml` I commented out the `theme: minima` line and added
   `remote_theme: thelehhman/plainwhite-jekyll`
2. In this file, add as well some theme related options, e.g.
   ```yaml
   plainwhite:
      name: Your name
      tagline: A short description of your job
      date_format: "%d %b %Y"
      show_excerpts: true
      navigation:
         - title: Resume
           url: "/resume"
   ```
   One more trick: The tagline accepts HTML tags. Thus, when I needed to add a breakline on it, I 
   just enveloped the lines with the `<br></br>` tags. You may see the result below my name at 
   your left side.
3. This theme has the option for you to have a profile picture. I did not wanted to use a photo,
   thus I needed an avatar. I found a site named [avatar maker](https://avatarmaker.com/) which
   offers a free tool for avatar generation. Then, I just saved the image as `portfolio.png` in a
   folder called `assets`. 
4. Since we changed the `_config.yml` file, we must kill the server (close the terminal it is 
   running or type Ctrl+c) and execute it again for the changes to take effect (`bundle exec 
   jekyll serve`)

## 4. Fill with content

Now is the time to fill content into the blog. Entries are made by creating markdown files
in the folder `_posts` of your project. The files names must follow the formula 
`YYYY-MM-DD-title.md`. In addition, on the top of the file, you may add

```
---
layout: post
title:  "The title of your post"
date:   2020-01-05 15:02:13 -0300
categories: tag1 tag2 
---
```

The possible layout value varies with the theme you choose. The categories values are the keywords of your post. Useful for you finding them later. Date is the date you created the post.

You may also edit the `index.markdown` to edit the content of your homepage.

## 5. Reviewing and Publishing

So, now you have everything set up and the site is running locally. It is time to publish it. However, 
it is a good idea before throwing it in the wild, to at least verify with a spell checker. One may use 
aspell. However, since I am using VS Code, I will the route of using an extension. My choice of weapon
is the 
[Code Spell Checker extension](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker).
I install it as any other extension and after a reload it points some spelling mistakes I did while 
writing this post.

Finally, it is time to create the repository on GitHub and publish the changes. To do so:

1. Create a new public repository in GitHub named `<githubusername>.github.io>`.
2. On your local folder, initialize the git repository: `git init`
3. Now, set up the url to upload your site to GitHub: 
4. Add the files of your project: `git add file1 file2`
   * The files you need to add are:
     -  Everything under `_posts` and `assets`
     -  `GemFile` (however, not `GemFile.lock`)
     -  `index.markdown`
     -  `404.html`
     -  `.gitignore`
     -  `_config.yml`
   `git remote add origin git@github.com:<githubusername>/<githubusername>.github.io.git`
5. Commit the changes with `git commit -m "<A short descriptive message of changes>"` followed by `git push origin master`

Now your site must be up and running. Notice that any changes you perform from now on that 
you desire to publish, you just add the relevant files, commit them, and pull to the origin 
(steps 4 and 5).
 
