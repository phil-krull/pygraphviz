# Django Models as ERD’s

# Django Models as ERD's

Creating Django models can be confusing because so much is done for us without visual aids like the ERDs in MySQL Workbench. (Though later on, we’ll get to use something called an **Admin Portal** that will help us with this.)

To help ease us into the comfort of the using migrations to generate the Django Models, let’s look at how we would approach a few different databases, and what the ERD would look like. Creating Django models can be confusing because so much is done for us without visual aids like the ERDs in MySQL Workbench. To help ease us into the comfort of the using migrations to generate the Django Models, let's look at how we would approach a few different databases, and what the ERD would look like.

_Note: The following extension installation is **advanced** and not required. _One cool extension is [Django Extensions](https://github.com/django-extensions/django-extensions), which you can `pip install` and add to your `settings.py` file since it’s a Django App itself. You may need to install a few dependencies on your machine to get this completely working.  There will probably be some errors to figure out regarding pygraphviz:

So this takes a little bit of work. Before you follow the directions below, here are the skills you would need:

**PC Skills:**

*   Establishing path variables,
*   Downloading binaries and installing binaries (msi files s)
*   Installing from downloaded wheels

**Mac Skills:**

*   brew installing
*   git cloning
*   running python setup.py files with dependencies.

**Directions For PCs:**

1.  [http://www.graphviz.org/Download_windows.php](http://www.graphviz.org/Download_windows.php)
2.  Download graphviz 2.38
3.  This should load toC:\Program Files(x86)\Graphviz2.38\
4.  Add “C:\Program Files (x86)\Graphviz2.38\bin\” to your environment path.
5.  Close and reopen command prompt and type: ‘where dot’ (hopefully it shows the path from 4 plus dot.exe)
6.  Navigate to and activate your djangovirtualenvironment
7.  pip install django-extensions
8.  pip install pygraphviz
9.  pip install pydotplus

**Directions for MACs:** Pretty straightforward. To reiterate: We created a `name` column and a `description` column, one with the Column_Type as a `CharField` and the other as a `TextField`. But notice how there isn't an `ID` column... _This gets created by Django on our behalf._

1.  brew update
2.  brew install graphviz
3.  navigate to and activate your djangovirtualenvironment
4.  git clone [https://github.com/pygraphviz/pygraphviz.git](https://github.com/pygraphviz/pygraphviz.git)
5.  Change directory to “pygraphviz”
6.  python setup.py install --include-path=/usr/local/Cellar/graphviz/2.38.0/include/graphviz --library-path=/usr/local/Cellar/graphviz/2.38.0/lib
7.  pip install django-extensions
8.  pip install pydot

Let’s build the equivalent of the following ERD diagram in Django: Let's build the equivalent of the following ERD diagram in Django:

![](http://s3.amazonaws.com/General_V88/boomyeah/company_209/chapter_3834/handouts/chapter3834_7234_blogs2.png)

Notice the `many_to_one` relationship; _one user can be associated with many posts_. Here’s the equivalent Django code: Notice the `many_to_one` relationship; _one user can be associated with many posts_. Here's the equivalent Django code:

<pre data-language="python">  # Inside models.py
</pre>
