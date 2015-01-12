=========================
 Eniram developers' blog
=========================

Cloning the repository
======================

::

    git clone <login>@rd01.eniram.fi:/rd/git/rd/devblog.git devblog
    cd devblog
    git clone -b gh-pages git@github.com:EniramLtd/devblog.git blog/html
    virtualenv -p python3.4 venv
    . venv/bin/activate
    pip install -r requirements.txt
    python setup.py develop

Creating a new draft
====================

::

    devblog -d "The Title of the Post"
    edit drafts/the_title_of_the_post.rst

Previewing the draft
====================

::

    devblog --preview drafts/the_title_of_the_post.rst

Promoting a draft to a post
===========================

::

    devblog -p drafts/the_title_of_the_post.rst

Compiling the blog to HTML and deploying to GitHub pages
========================================================

First compile and verify the blog::

    devblog -b
    # browse devblog/blog/html/index.html locally and verify all is ok

Then commit changes to the source repository::

    git add -A
    git commit -m "<message>"
    git push

Finally, deploy the compiled blog to GitHub Pages::

    cd blog/html
    git status
    git add -u
    git commit -m "<message>"
    git push
    cd ../..
