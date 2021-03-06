Scala Vim Snippets
==================

I just took the Scala snippets from TextMate and put them in a snipMate
.snippets file.

Installation
------------
If you are in UNIX-land, you should be able to use `make install` to install
them.

If you are on Windows, copy the snippets file into your \_vim\snippets folder.
You'll know where this is better than I do.

`make extract` moves your scala.snippets file from your ~/.vim/snippets back to
the working directory so you can check them in.

The Makefile really might be the simplest thing you've ever seen.

Syntax Checking
---------------
It's quite possible when you are copying and pasting snippets files together to
bugger up the syntax. check.rb is a Ruby script that checks each line of the
script using the regex provided by the syntax file for snipMate snippets files.
`make check` will syntax check the file for you.

smDoc
-----
smDoc creates HTML and PDF documentation from snipMate files. HTML generation
is done using the smdoc.rb tool - invoked using `make doc-html`.

The point of smDoc is to produce printable PDFs - so you can print it out and
carry it around with you as a cheatsheet/flashcard type thing.

The HTML documentation generation uses a simple
[JavaDoc](http://java.sun.com/j2se/javadoc/)-style syntax - for each snippet
entry, you can prefix it with a line that starts "## ". In there, put as much
description as you want to. You can use inline HTML if you like, but try to
keep the descriptions short and snappy. It renders these into a definition list
(the dl, dt, dd tags).

As well as this, you need to produce a small file called metadata.yml which
contains the name of the programming language or tool you have written the
snippets file for, the name of the primary author and a contact e-mail
address. This is written in [YAML](http://www.yaml.org/).

PDF generation is currently for OS X only. It uses a RubyGem called
[wkpdf](http://plessl.github.com/wkpdf/) which uses the
[WebKit](http://webkit.org/) engine on the Mac to render a PDF. This can be
invoked using `make doc-pdf-a4` and `make doc-pdf-letter`. 

Blather
-------

Key snippets:

  * <var>class</var>
  * <var>cclass</var> ([case class](http://www.scala-lang.org/node/107))
  * <var>trait</var> ([documentation](http://www.scala-lang.org/node/126))
  * <var>object</var>
  * <var>application</var>
  * <var>def</var>
  * <var>if</var>, <var>ifelse</var>
  * <var>try</var>
  * <var>tfc</var> (try, catch, finally)
	* bizarre name, I know, but it's how it is in the TM bundle. If other
	  people find this particularly annoying, I'll fix it
  * <var>match</var>, <var>case</var> ([pattern matching](http://www.scala-lang.org/node/120))
  * <var>p</var> (println)
  * <var>main</var>
