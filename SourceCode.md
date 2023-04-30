# CodeSnip Compiling & Source Code FAQ

This FAQ is about compiling and using the source code of the DelphiDabbler [**CodeSnip**](https://github.com/delphidabbler/codesnip) Code Snippets Repository Application.

> If your question was about using CodeSnip itself please see the [Using CodeSnip FAQ](./UsingCodeSnip.md) instead.

If you can't find an answer to your question below, and you've read the program's help file, read-me etc., then create an issue on GitHub (GitHub account required).

> Please note that **CodeSnip version 3 and earlier are no longer supported,** This FAQ covers version 4 only

## Contents

1. [Where can I get the CodeSnip source code?](#faq-1)
2. [Which compiler is needed to compile CodeSnip?](#faq-2)
3. [Is CodeSnip open source?](#faq-3)
4. [How do I build CodeSnip from source?](#faq-4)
5. [Do you have a version of the source code that compiles with Delphi versions earlier than Delphi XE?](#faq-5)
6. [Will you publish the PHP source code for the web services that CodeSnip accesses?](#faq-6)
7. [I want to use some of the CodeSnip source code in my project, what are the rules?](#faq-7)
8. [How do I contribute code / bug fixes to the project?](#faq-8)
9. [How do I use TortoiseSVN to check out the CodeSnip source code?](#faq-9)
10. [Can I use CodeSnip source code in my GPL or LGPL licensed project?](#faq-10)
11. [Why are you still using Delphi XE to compile CodeSnip?](#faq-11)

## FAQ 1

**Where can I get the CodeSnip source code?**

The best place is the [CodeSnip Git repository](https://github.com/delphidabbler/codesnip) on GitHub.

CodeSnip 4 is now developed using the [Git Flow](http://nvie.com/posts/a-successful-git-branching-model/) methodology. The latest release of CodeSnip is available from the `master` branch. Development takes place on branches off `develop`. Tags in the form `version-x.x.x` are used to denote each release, where `x.x.x` is the version number of the release.

> ℹ️ The repository contains branches other than `master` and `develop` but none of these branches contain production code.

## FAQ 2

**Which compiler is needed to compile CodeSnip?**

CodeSnip is written in Delphi Object Pascal. The current code base is compiled using Delphi XE. See [FAQ 11](#faq-11) for an explanation.

Some other utilities are also needed. See the "Build Tools" section of [`Build.html`](https://htmlpreview.github.io/?https://github.com/delphidabbler/codesnip/blob/master/Build.html)<sup>1</sup> for details.

<sup>**1**</sup> the linked file relates to the current release. Versions for other releases etc. may vary. Look at the file `Build.html` for the release you are interested in.

### FAQ 3

**Is CodeSnip open source?**

CodeSnip's original code is open source.

The [Mozilla Public License 2.0](http://www.mozilla.org/MPL/2.0/) is used for most of the original source code. For full details see the Source Code section of CodeSnip's [License file](https://htmlpreview.github.io/?https://github.com/delphidabbler/codesnip/blob/master/Docs/License.html)<sup>1</sup>.

Third party code uses a variety of open source licenses. Any third party libraries are also open source.

The only exception is the code linked in from the Delphi RTL and VCL libraries. Given that you need Delphi to compile CodeSnip, that's not really an issue providing you don't distribute the Delphi library source code.

<sup>**1**</sup> This license file relates to the current release. Versions for other releases etc. may vary slightly. Look at the file `License.html` for the release you are interested in.

## FAQ 4

**How do I build CodeSnip from source?**

This is all covered in detail in the file [`Build.html`](https://htmlpreview.github.io/?https://github.com/delphidabbler/codesnip/blob/master/Build.html)<sup>1</sup> that can be found in the "root" of each source code release.

<sup>**1**</sup> the linked file relates to the current release. Versions for other releases etc. may vary. Look at the file `Build.html` for the release you are interested in.

## FAQ 5

**Do you have a version of the source code that compiles with Delphi versions earlier than Delphi XE?**

No, sorry.

The code base might, with a few changes, compile with Delphi 2009/2010, but that is not guaranteed. But, since the code now assumes that `string = UnicodeString` it definitely can't be compiled with anything before Delphi 2009.

## FAQ 6

**Will you publish the PHP source code for the web services that CodeSnip accesses?**

No, I'm not releasing the web server source code. Sorry. The code is not open source.

Why? Two reasons. Firstly the code is a mess! It has dependencies throughout the entire web site code base. Secondly, releasing the code could compromise security.

> **Note 1:** CodeSnip v4.16.0 and later no longer use web services.
> 
> **Note 2:** The delphidabbler web services closed down in June 2020.

## FAQ 7

**I want to use some of the CodeSnip source code in my project, what are the rules?**

The following assumes that the code is covered by the Mozilla Public License (MPL) [v1.1](http://www.mozilla.org/MPL/1.1/) or [v2.0](http://www.mozilla.org/MPL/2.0/).
 
> **This answer is not authoritative** - please refer to the relevant license text for that. This is just a brief overview for which I make no warranty of accuracy. If this answer conflicts with the licenses then the relevant license takes precedence.

If your project is for private use (i.e. you will not be distributing the project) then you can use the code as you wish.

If you do intend to distribute your project, then the following rules apply to the original CodeSnip code.

1. If you just use one or more source files unchanged you must not change the MPL license statement in the file's header comments. You must also advertise<sup>1</sup> that your product uses some MPLd code and provide a means by which users can obtain the source code<sup>2</sup>.
2. If you modify one or more source files then leave the header comment relating to the license unchanged. You must then advertise<sup>1</sup> the use of MPLd code and provide a means to obtain the modified source files<sup>3</sup>.
3. If you copy and paste some code from one of the MPLd source files into one of your own source files then that file must also adopt the MPL. You must add a suitable<sup>4</sup> MPL license block to the source file. As you will now expect you must advertise<sup>1</sup> that the product contains MPLd code and provide a means to obtain the relevant files<sup>3</sup>.

Using MPLd code from CodeSnip **does not** mean you have to make your other source files available. But there's no way out of complying with these requirements for MPLd code.

If you want to use any MPLd code in a GPL or LGPL project please read [FAQ 10](#faq-10).

Footnotes:

<sup>**1**</sup> "Advertise" means you must mention that your product uses MPLd code in some suitable place in your documentation, help files, about box etc. The documentation must also tell users how to obtain the source code. If you are using any MPL v1.1 files you must also acknowledge the names of their original developers.

<sup>**2**</sup> In the case of unchanged source files you may link to the [CodeSnip Git repository](https://github.com/delphidabbler/codesnip) on GitHub, providing that you specify the names, paths and commit ids of the files you are using. Alternatively provide your own means of obtaining the files<sup>3</sup>.

<sup>**3**</sup> Make your own arrangements for making the MPLd source code available to users of your project. You could upload the files to some web space and provide a URL in your documentation or distribute the source files with your product.

<sup>**4**</sup> "Suitable" here means that the version of the license you use should be the same as that covering the source file that the code was copied from. So what about the case of copying code from files covered by different versions of the license? Just don't do it!

## FAQ 8

**How do I contribute code / bug fixes to the project?**

Contributions are welcome. Just fork the project's [Git repository](https://github.com/delphidabbler/codesnip) and create a feature branch off the `develop` branch. Commit your changes to your feature branch then submit a pull request when ready.<sup>1</sup>

> ⚠️ The repository contains branches other than `master` and `develop` but ***none of these branches are accepting contributions.***

Do not change the license on any code you modify. If you are submitting new source code units please license them using the [Mozilla Public License v2.0](http://www.mozilla.org/MPL/2.0/) without an "Incompatible With Secondary Licenses" Notice. If you don't want to use the MPL v2.0 please discuss it with me by raising an issue on the [Github repo](https://github.com/delphidabbler/codesnip).

<sup>**1**</sup> For info on checking out code from the Git repository, see [FAQ 1](#faq-1).

## FAQ 9

**How do I use TortoiseSVN to check out the CodeSnip source code?**

You can't anymore. CodeSnip source has been moved to a [Git repository](https://github.com/delphidabbler/codesnip) on GitHub.

## FAQ 10

**Can I use CodeSnip source code in my GPL or LGPL licensed project?**

This answer covers files using the Mozilla Public License (MPL) [v1.1](http://www.mozilla.org/MPL/1.1/) or [v2.0](http://www.mozilla.org/MPL/2.0/). For other licenses, please read the license concerned and check out what the [Free Software Foundation](http://www.fsf.org/) has to say about it.

> **This answer is not authoritative** - please refer to the relevant license text for that. This is just a brief overview for which I make no warranty of accuracy. If this answer conflicts with the licenses then the relevant license takes precedence.

Whether the source code can be used in GPL / LGPL projects depends on the version of the MPL used by the source code files in question. Each file contains a header comment that identifies the license.

### MPL v2.0

If the source file is covered by the MPL v2.0 then it can usually be used in your GPL or LGPL project since the MPL v2.0 is compatible with the GPL and LGPL.

There is an exception though. MPL v2.0 files may carry an "Incompatible With Secondary Licenses" notice which reads:

> `This Source Code Form is "Incompatible With Secondary Licenses", as defined by the Mozilla Public License, v. 2.0.`

If this statement is present the file becomes incompatible with the GPL / LGPL.

If you include MPL 2.0 code in your project you must distribute a full copy of the license with it: see http://www.mozilla.org/MPL/2.0/.

### MPL v1.1

The MPL v1.1 and the GPL / LGPL are not considered to be compatible. Therefore you can't use MPL v1.1 code in your project.

There is an exception in the case of source code covered by the MPL / GPL / LGPL tri-license which is GPL / LGPL compatible.

## FAQ 11

**Why are you still using Delphi XE to compile CodeSnip?**

When Delphi XE2 was released I attempted to compile CodeSnip with it but XE2 would not compile it. The reason was that XE2 ran out of memory! A complete restructure of the program into separately compiled libraries would have been required to get the program to compile. That wasn't (and still isn't) something I'm prepared to do.

I eventually updated to Delphi XE4 and that had the same problem. 

After XE4 I didn't update Delphi for a long time. Not until 2021, in fact, when I acquired Delphi 10.4 Sydney followed by Delphi 11 Alexandria.

Now Delphi 11 _will_ compile CodeSnip without choking. But there have been sufficient changes in the compiler and libraries to make the compilation fail. However a few changes to CodeSnip's source code do enable compilation to succeed, albeit with numerous warnings and hints. The trouble now is that the Delphi 11 compiled program crashes on closure with a memory access error. Even worse, the UI is corrupted and the main menu is not displayed! The unaltered code compiled with Delphi XE is fine. After several hours of investiagtion the number of bugs seems to be growing rather than reducing.

So, at least for now, it's XE or nothing I'm afraid.

> **Note:**
> 
> The previously announced attempt at a ground up rewrite of CodeSnip with Delphi 11 (code named [`belvedere`](https://github.com/delphidabbler/codesnip/tree/belvedere)) got nowhere and has been abandoned. A further, unannounced, attempt (code named [`caboli`](https://github.com/delphidabbler/codesnip/tree/caboli)) also failed.
> 
> One (final) attempt to update to Delphi 11 is being considered, but has not yet been announced. Watch the [CodeSnip Blog](https://codesnip-app.blogspot.com/) for any future announcement, but don't hold your breath.
