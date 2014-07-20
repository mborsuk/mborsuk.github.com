---
layout: post
title: Using vim key bindings in IPython Notebook cells
---

The [IPython Notebook](http://ipython.org/notebook.html), a computation
environment I spend a lot of time in, uses [CodeMirror](http://codemirror.net)
for interactive editing of cells.  CodeMirror [supports vim]
(http://codemirror.net/demo/vim.html) key bindings (as well as emacs and
sublime text) but it was not immediately obvious how to enable this for IPython
Notebooks.  In the profile directory for your running notebook server, simply
add the following to static/custom/custom.js:

{% highlight javascript %}
$.getScript("static/components/codemirror/keymap/vim.js")
IPython.CodeCell.options_default.cm_config["keyMap"] = "vim"
{% endhighlight %}
