This plugin enables Subversion revision control in FitNesse. The plugin is intended to perform basic operations like opening pages for edit, delete, add and revert files if neccessary. Remember that each page is defined by a directory that bears it's name, and two files that contain it's content. The first file is content.txt which holds the wiki text. The second is properties.xml which holds all the metatdata for the page. Unlike other svn plugins, this plugin does not commit changes the user has to take care on his own to submit these files.

This plugin is based on Markus Gärtner's PerforceCmSystem plugin see http://code.google.com/p/perforcecmsystem/

It differs from Yuval Oren's version at http://code.google.com/p/cm-subversion/ in that it does not commit each change.

You must also include SvnCmSystem on the classpath when starting FitNesse.
An example how to do this is included in the distribution.

When you have started up FitNesse with the SvnCmSystem in your classpath,
you have to set CM\_SYSTEM to fitnesse.wiki.cmSystems.SvnCmSystem.
This can be done in one of three ways:

1) use
> !define CM\_SYSTEM {fitnesse.wiki.cmSystems.SvnCmSystem}
> on the top-most page within FitNesse,
2) start FitNesse with -DCM\_SYSTEM=fitnesse.wiki.cmSystems.SvnCmSystem or
> some other way to set the CM\_SYSTEM property within the JVM,
3) export the environment variable CM\_SYSTEM with the content
> fitnesse.wiki.cmSystems.SvnCmSystem. How to do this is shell dependent.

After having started FitNesse with the proper classpath addition and the
CM\_SYSTEM variable defined to the SvnCmSystem class, FitNesse should use
Subversion when you add a page, edit one, refactor one, having the according
content.txt and properties.xml files being added or deleted from the changelist.