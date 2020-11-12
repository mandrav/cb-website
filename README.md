# Code::Blocks web site

These are the source files for the [Code::Blocks website](https://www.codeblocks.org).
The site is build using [Hugo](https://gohugo.io), a static site generator.

## History

We used to use [Joomla](https://www.joomla.org) for the old version of the site. While Joomla worked generally OK, it was also a big CMS which, in the end, we had no need for.

We had to always keep on top of updates (like with any CMS), as it's one of the favorite things for hackers to try to hack. This got tiring at some point so we got left with an older version (v1.5), almost impossible to upgrade anymore...

Thankfully, our site was never hacked but we consider this to be just a happy coincidence rather than being owed to our successful hardening/securing.

## The way forward

It is clear that we don't have much use for the fancy features modern CMSs offer.
What we really need is a simple way to create new posts/articles and occasionally update the way our site looks (i.e. theme).
The easier it is for us to do these things, the most often we 'll want to update our site!

So we decided to make the switch and start using a static site generator to build our site from simple markdown files.
After trying a bunch of static site generators we decided to settle with [Hugo](https://gohugo.io). It is very fast, has a big community and is very easy to use.

## How it works

[Hugo](https://gohugo.io) comes as a single binary, named `hugo`.
Typing `hugo help` gives us an overview:
```shell
hugo is the main command, used to build your Hugo site.

Hugo is a Fast and Flexible Static Site Generator
built with love by spf13 and friends in Go.

Complete documentation is available at http://gohugo.io/.

Usage:
  hugo [flags]
  hugo [command]

Available Commands:
  config      Print the site configuration
  convert     Convert your content to different formats
  deploy      Deploy your site to a Cloud provider.
  env         Print Hugo version and environment info
  gen         A collection of several useful generators.
  help        Help about any command
  import      Import your site from others.
  list        Listing out various types of content
  mod         Various Hugo Modules helpers.
  new         Create new content for your site
  server      A high performance webserver
  version     Print the version number of Hugo

... (snipped)

Use "hugo [command] --help" for more information about a command.
```

For our use, we really only need a couple different invocations of `hugo`:

* `hugo new <some content filename>`
* `hugo serve -D`

## Adding new content

When running the `hugo new ...` command, we 're really creating a new file under the `content` directory.
So to create a new article/post named "The way forward", we just have to run:

```hugo new post/the-way-forward.md```

We just need to keep the naming right because that is how it will end up in the final URL. So the above example new post would be reachable by going to **https://www.codeblocks.org/post/the-way-forward**.

And that's it! See? Being that easy, we may just update the site more often ;).

## Previewing the site

[Hugo](https://gohugo.io) also provides a development web server to preview our site, even with live reloading!
Just run `hugo serve -D` in the root directory (where this README file is).
Nothing more to say about that.

## Publishing the changes to the world

Well, we 've added new articles to the site, created new pages and everything works fine with the development server.

But the world can't see it.
It's only available on our workstation...
We have to publish it somehow to the real web server that is serving [Code::Blocks](https://www.codeblocks.org).

Well, all we have to do is just commit our changes and push them to our repository!
That's all it takes for the live site to rebuild and refresh, thanks to the hard work we 've been putting to our infrastructure these last few weeks.

We don't think it could be made any easier than this!

> This means we 're now open to the public! If you spot a typo or another error on our site you could submit a pull request for us to see and apply the fix! We **do** need the community's help.

## Closing words

This is just a small part of all the changes we 've been making the last few weeks to improve our infrastructure and bring it to the modern age.
We hope this can only help to bring a better future for the project.
