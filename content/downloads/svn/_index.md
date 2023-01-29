---
title: "Retrieve from SVN"
date: 2020-03-29
draft: false
aliases:
  - 7
---

To retrieve the source code from [SVN](https://subversion.apache.org), you need to have a client for SVN installed. There are many SVN clients ranging from command-line programs over cross-platform applications (like [SmartSVN](https://www.smartsvn.com)) to full-blown shell extensions (like [TortoiseSVN](https://tortoisesvn.net) for Windows).

Regardless of which SVN client you use, the basic settings to access the Code::Blocks source code are essentially the same.

### Anonymous access via SVN protocol:

Repository URL:

    svn://svn.code.sf.net/p/codeblocks/code/trunk

Sample command line:

    svn checkout svn://svn.code.sf.net/p/codeblocks/code/trunk

### Anonymous access via HTTP protocol:

Repository URL:

    https://svn.code.sf.net/p/codeblocks/code/trunk

Sample command line:

    svn checkout https://svn.code.sf.net/p/codeblocks/code/trunk

---
 
### Notes:

Our repository uses the standard layout proposed by Subversion. This means there are trunk, tags, and branches top-level folders. The commands above refer to the trunk directory, which contains the current development code. Bleeding edge at its finest!

If you want to access the source code of stable releases, you can find it under the tags directory. For example, the source code of Code::Blocks 20.03 can be accessed in tags/20.03. So the command-line to retrieve it using the SVN protocol would be:

    svn checkout svn://svn.code.sf.net/p/codeblocks/code/tags/20.03
