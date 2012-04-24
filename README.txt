Introduction

I've been using Dreamweaver for several years now, even before it was actually a beneficial tool. Now, it seems, I can't live without it. So when I started a new job with a company that was heavily using Velocity with JBoss I quickly became frustrated with the lack of compatibility with Dreamweaver. I tried finding an extension or some type of support, but all I could find were multiple requests for such. I had written several Flash Extensions by then, so I decided to take the plunge into creating the Velocity Suite extension. It's far from perfect, but so far I've been very happy with the results.

 

Features

Gives full Velocity (VTL) funcitonality to Dreamweaver, including the following:

1. Inserts a "Velocity" object with tools to automatically insert VTL code into your document. (appears as "Insert" tab in MX 2004 and up).
2. Adds Velocity's .vm extension in DreamWeaver and associates .vm files with Dreamweaver.
3. Adds "Velocity" as a new document type in Dreamweaver. Also adds a Default.vm page which will open as the new document when Velocity is selected.
4. Let's .vm files act as thought they were .html files, including color coding, tag hints, etc.
5. Adds Third Party Tag support.
6. Adds Translators for #include and #parse, making the included file visible in the design view.

Note: including multiple files within a single #include statement [i.e. #include( "disclaimer.txt", "opinion.txt" ) ] is not currently supported by Third Party Tags or Translators in this extension.

 

Best Practices

If you plan to use the extension, there are a few things to keep in mind for it to work properly:

First and foremost is the way you format your VTL (Velocity Template Language). The final closing paren ')' must be preceded by a space, no other closing paren can be preceded by a space.

For example:
#set ( $foo = (4-5) ) will work,
but #set ( $foo = (4-5 ) ) will break and
#set ($foo = (4-5)) will also break.

I have created a .dwr search query that will try to find velocity code that does not meet this standard and replace it with the correct spacing. I use the .dwr quite a bit, especially when I need to open a document in Dreamweaver that has been created by someone else on my team who has coded without using this standard. I recommend using "replace" rather than "replace all" in conjunction with this search because it is not fool proof.

Download the .dwr search query file

For information on how to use a .dwr file, see "Saving a Find and Replace query" or check the documentation that comes with Dreamweaver. (Note: the above link refers to Dreamweaver 4, but still applies to current versions.)

The other thing you may want to add to your documents (although not nearly as important as the affore mentioned), is the code coloring functionality. The Velocity Suite extension already automatically colors .vm documents as though they were .html documents, but to invoke Velocity code coloring you must have #* velocity document *# somewhere at the beginning of your .vm or .html document. The only thing this does is turn your VTL tags blue. I honestly rarely use this feature, but it's there if you want it.

 

Version History

Latest version 1.2.3: released July 2, 2006
Verson 1.2.3 	Replaces translators which were missing in 1.2.2.
Verson 1.2.2 	Contains a minor bug fix in Color Coding.
Verson 1.2.1 	Revised support info added to the file itself including email address and URL to this page.
Verson 1.2.0 	Added translators for #include and #parse. In other words, the content of the file included will apear in the design window.
Verson 1.1.4 	Fixed a conflict with how dreamweaver handles other includes such as asp and ssi.
Verson 1.1.3 	Enhanced color coding support
Verson 1.1.2 	Enhanced macro support including how the macro button on the Velocity Toolbar works as well as how Third Party Tags handle macros.
Version 1.1.0 	Added Third Party Tag support which replaces VTL in design view with "sheild" images.
Version 1.0.4 	Fixed lack of vtl tag hints and vtl code coloring missing in previous versions
(previous versions were undocumented)

 

Known Issues

Issue: When either #include or #parse are used, MM:BeginLock code appears and messes everything up.
Solution: Make absolutley sure that you are following the best practices guidelines. Having the wrong use of spaces with parentheses is almost certainly the cause of this issue. If you saw this problem, then fixed your spacing, and are still seeing MM:BeginLock code, it is probably just residual from before and must be manually fixed. If you hate this bug really bad, I've created Velocity Suite Lite which does not use #include and #parse translators. Using that version of the extension should make this problem disapear completely, but you won't be able to preview your include files in Dreamweaver's design window. 