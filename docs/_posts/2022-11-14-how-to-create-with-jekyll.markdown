---
#layout: single
title:  "How this site was created!"
date:   2022-12-14 19:00:35 +0800
categories: jekyll update site
---


If you wonder how this site was created, this post will give you detailed instruction on how to create a website using github pages with Minimal Mistakes remote theme having a landing page and header with navigation to the other pages of the site. 

The site was created using using Github Pages with Minimal Mistakes remote theme:

1\. Create a new repository on GitHub with the name **`<username>.github.io`**, where **`<username>`** is your GitHub username. This will create a special repository that GitHub Pages will use to serve your website.

2\. Clone the repository to your local machine using **`#git clone https://github.com/<username>/<username>.github.io.git`**.

3\. Create a new file called **`index.md`** in the root directory of the repository. This will be your landing page.

4\. Copy the following code into **`index.md`** to create a simple landing page:
   {% highlight yaml %}
   ---
   layout: home
   ---
   {% endhighlight %}

5\. Commit and push the changes to GitHub.

6\. Next, we'll set up the Minimal Mistakes remote theme. In your terminal, navigate to the root directory of your repository and run the following commands:
   {% highlight bash %}
   git submodule add https://github.com/mmistakes/minimal-mistakes.git
   cd minimal-mistakes
   git checkout tags/4.22.0
   cd ..
   {% endhighlight %}
   This will add the Minimal Mistakes theme as a submodule to your repository and checkout a specific version (4.22.0) that's compatible with GitHub Pages.

7\. In the root directory of your repository, create a new file called **`_config.yml`**. This is where you'll configure the Minimal Mistakes theme.

8\. Copy the following code into **`_config.yml`**:
   {% highlight yaml %}
   remote_theme: mmistakes/minimal-mistakes@4.22.0
   
   title: Your Site Title
   description: Your site description
   
   author:
     name: Your Name
     email: your.email@example.com
     url: yourwebsite.com
   
   # Navigation links
   nav:
     - title: About
       url: /about/
     - title: Blog
       url: /blog/
     - title: Contact
       url: /contact/
   {% endhighlight %}
   Replace Your Site Title, Your site description, Your Name, your.email@example.com, and yourwebsite.com with your own information. The nav section defines the navigation links that will appear in your header. You can add or remove links as needed.

9\. Commit and push the changes to GitHub.

10\. Finally, create additional pages for your site by creating new Markdown files in the root directory of your repository. For example, to create an About page, create a new file called about.md with the following content:
    {% highlight yaml %}
    ---
    layout: single
    title: About
    permalink: /about/
    ---
    
    This is the About page.
    {% endhighlight %}

11\. Commit and push the changes to GitHub.

Your website should now be live at <username>.github.io, and you should see a header with navigation links to your other pages.

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
