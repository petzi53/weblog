---
authors: 
- Peter Baumgartner
draft: no
date: "2017-09-10"
slug: how-to-install-disqus-on-hugo
summary: This post explains how to integrate Disqus as a discussion forum for your
  website. It is not a thing you can do directly applying the Hugo documentation because
  there is a faulty template to change.
categories:
- blog engines
- how-to
- static sites
tags:
- hugo-academic
- blogdown
- hugo
- disqus
title: How to install Disqus on Hugo?
---

### Steps to intgrate Disqus into your Hugo website

1. **Sign up**: First of all you have to sign up for [Disqus](https://disqus.com/). {{< figure src="/img/disqus/sign-up.png" title="Create an account on Disqus." numbered="true" >}}

2. **Install Disqus**: You are offered two choices after the registration process. Select 'I want to install Disqus on my site'. {{< figure src="/img/disqus/two-choices.png" class="small" title="Choose 'Install Disqus'" numbered="true" >}}

3. **Fill in the form**: Disqus needs some information for adding a forum to your website. I will add just two remarks as the form is mostly self-explaining. Firstly, the website name is a text snippet that will appear in the head of every forum section. It does not have to be related to you website name. Secondly, make a note of your Disqus short name as you are going to use it in step 5 and 6. {{< figure src="/img/disqus/fill-in-form.png" title="Configure Disqus for your site" numbered="true" >}}

4. **Find discussion template**: With the next two steps we are going to fix the problem of a faulty Hugo template. Look for the file 'single.html' and open it in the editor to inspect the content. `single.html` should be under `/themes/<your-theme-nam>/layouts/_default`.  At the end of the file -- just before the footer --, you should find the name of the partial template for your discussion forum (= 'comments-html' in my case). {{< figure src="/img/disqus/find-discussion-template.png" title="Configure Disqus for your site." numbered="true" >}}

5. **Replace content**: Now go and edit this file, which should be found under `/themes/<your-theme-nam>/layouts/partials`. You have to replace the whole content with the [code snippet provided by Yihui Xie](https://github.com/rstudio/blogdown/issues/52#issuecomment-288407836) (Thanks a lot by the way!!). To help you, you can [compare my changes at GitHub](https://github.com/petzi53/weblog/commit/b7993533e501e2f1668375e22fe05e1ceb7d87ae?diff=split). But don't forget to change the URL to your Disqus account [as I did :blush:]! {{< figure src="/img/disqus/my-github-changes.png" title="Replace content of your partial template as explained" numbered="true" >}}

6. **Add shortname**: To finish the installation you have finally to add the line `disqusShortname = "<your-disqus-shortname>"` to your config.toml. {{< figure src="/img/disqus/add-disqus-shortname.png" title="Add your Disqus short name into the config.toml" numbered="true" >}}

7. **Congratulation!** You have integrated Disqus into your static website. Go to one of your posts and check it. Your end of the page should look similar as in the following graphic. {{< figure src="/img/disqus/disqus-integrated.png" title="Disqus forum successfully integrated" >}}

## Critical remark to Disqus

I should mention that there is growing skepticism in the community about Disqus. People are not only criticizing slowness (load-time behavior) but above all they are concerned about data integrity. It seems that there are lots of [irrelevant requests](http://donw.io/post/github-comments/) to track the data traffic for whatever purpose nobody knows. 


