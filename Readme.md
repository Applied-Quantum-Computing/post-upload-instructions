# How to upload a post

There are two parts to uploading a post. First, format post as a markdown file with YAML front matter. Second, "jekyll" markdown file to create site ready post.


### Format: export to markdown
Posts are stored in your 'Applied-Quantum-Computing.github.io/_posts' folder as markdown files (.md). Be sure to pull the repo before proceeding.

To export:
1. Export the jupyter notebook you want to be a post as a markdown file
    * start up the jupyter notebook, go to file, download as, then markdown
2. Name the markdown file with the format yyyy-mm-dd-title (the title can contain spaces)
3. Check the markdown file's special casing is generated with html (e.g. < strong > for bold) tags rather than markdown short cuts (e.g. \*\*bold\*\* for bold)
4. Check urls still make sense and are tied to other site articles.
5. When you exported the notebook to a markdown file, all plots and images should have also been exported as pngs in the same folder as the markdown file. Move these files to the folder 'Applied-Quantum-Computing.github.io/assets/images/'. In the markdown file, replace ```![png](auto_generated_filename.png)``` with ```![png](/assets/images/auto_generated_filename.png)``` for each image. Note, the png filenames are auto generated, but they need to be unique in the assets folder, so you may need to rename them to avoid filename conflicts.

### Format: YAML front matter
Here is an example of all/most of the YAML front matter we use in posts:
    
\---<br>
layout: post<br>
published: true<br>
title:  "Quantum Unsupervised Learning with Max-cut"<br>
author: AJ Rasmusson<br>
date: 2019-11-07<br>
mathjax: true<br>
front-image: "assets/images/output_17_0.png"<br>
source-code: "https://github.com/ajrazander/Unsupervised-QML/blob/master/Max-cut_vs_k-means.ipynb"<br>
commentary: |<br>
    <p>Quantum computing is supposed to enhance AI and machine learning, but this is the first time I've actually seen it in action.
    Most of this project is just me trying to understand how qaoa solving the max-cut problem can be used for machine learning (see details in code).
    The plan is to work through this then play around with it. Hopefully by playing around enough, I could find a way for small
    (< 50 qubit--<a href="https://arxiv.org/abs/1801.00862">NISQ</a> quantum computers to more quickly be powerful learning machines.
    <strong>UPDATE:</strong> If you want to see some of my playing arounds, check out <a href="https://ajrazander.github.io/unsupervised-machine-learning/max-cut/2019/11/13/Max-cut-2+-Divisive-Clustering.html">this other post</a>.</p><br>
tags: [unsupervised-machine-learning, max-cut, qaoa, ising-model, advanced]<br>
\---

Be sure to include \--- at the beginning and end of the front matter.
layout should always be post.<br>
published depends if you want it to show on that site or not yet.<br>
title needs to be in double quotes.<br>
author is your name!<br>
date is the date of the post release.<br>
mathjax should always be true.<br>
front-image is the path to the image you want to show when people are browsing posts. the path should always be "assets/images/" then your file name (as seen in the above example).<br>
source-code is a link to the original jupyter notebook if you want to share that.<br>
commentary is your time to talk with readers about the post. It is the first text they will see and is the only text shown when browsing posts.<br>
tags are tags. The more accurate your tags, the easier readers will find your post.<br>

### "Jekyll" post

To do this part, you need to install jekyll and its dependecies. See the [next section](#Setting-up-Jekyll-and-Ruby-and-Bundle) for more info.

Lastly, put your markdown file in the folder 'Applied-Quantum-Computing.github.io/_posts/'. Open a bash terminal, move to the folder applied-quantum-computing.github.io, and run ```bundle exec jekyll serve```. This will generate the website with the new post, and you're done!

### Push to repo
Don't forget to push to the repo!

# Setting up Jekyll

The best way to setup up Jekyll is to follow their [installation guide](https://jekyllrb.com/docs/installation/)—pure and simple.

Personally, I had a terrible time getting Ruby to the right version and getting Bundle to work correctly. Hopefully that doesn't happen for you as well. If you're having trouble, let <a href="mailto:quantumrepeater@gmail.com">us</a> know. If you push to the repo, we can pull, then jekyll it on own machines.
