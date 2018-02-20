## Creating pages

As well as having pages which describe your code, you can include your own pages, perhaps to give an overview of your project or provide details about how people can raise issues.

All pages will be formatted using the simple but powerful markup language [reStructuredText(ReST)](http://docutils.sourceforge.net/rst.html), this [quick ref](http://www.sphinx-doc.org/en/stable/rest.html) show's to use the most common functions.

To get started lets create an **about** page which will display some details about the project and where to find out more information.

+ Create a new file called `about.rst`.

+ Add a title to the page:

```
About this project
==================
```

+ Add some content about the project e.g.

```
Deck of cards is set of classes for creating playing cards.
```

+ Perhaps add a hyperlink to the projects sourcecode.

```
You can create this project yourself by visiting \`this page <https://projects.raspberrypi.org/en/projects/deck-of-cards>\`_.
```

--- collapse ---

---
title: URLs in ReST
---

The structure of the URL markup is very specific.

The text for the URL, and the URL itself is between 2 back ticks `\`` and is terminated with an underscore `_`.

```
\`link_text <url>\`_
```

It is important to put a space between the `link_text` and the `<url>`.

This type of markup is referred to as **in line** because it is within the markup.

You can also create seperate url definitions, which are useful if you want to link to the same URL twice.

```
Please visit the \`raspberry pi\`_.

.. _raspberry pi: http://raspberrypi.org/
```

--- /collapse ---

+ When you finished creating your `about` page add it to the `index.rst` file.

```
Welcome to card's documentation!
================================

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   about
   code
```

+ Rebuild your project to see your new page.

![project about page](images/path)

+ Add a 2nd page to your project e.g. a **faq** page.