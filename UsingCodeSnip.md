# Using CodeSnip FAQ

This FAQ is about using version 4 of the DelphiDabbler [**CodeSnip**](https://github.com/delphidabbler/codesnip) Code Snippets Repository Application.

> If you have questions about compiling CodeSnip or using its source code please see the [Compiling & Source Code FAQ](./SourceCode.md).

If you can't find an answer to your question below, and you've read the program's help file, create an issue on GitHub (GitHub account required).

> Please note that **CodeSnip version 3 and earlier are no longer supported**, This FAQ covers version 4 only.

## Contents

1. [I'm test compiling code within CodeSnip and get compiler warnings I don't want. Can I switch them off?](#faq-1)
2. [Why can't I edit snippets from the on-line database?](#faq-2)
3. [What changes does CodeSnip make to my system?](#faq-3)
4. [What personal information is stored by CodeSnip?](#faq-4)
5. [How do I get CodeSnip to use a proxy server to access the internet?](#faq-5)
6. [How do I cross-reference my snippets using the "See also" field?](#faq-6)
7. [Delphi XE2 generates a "F1026 File not Found ?????.dcu" error when test compiling snippets. What's going wrong?](#faq-7)

## FAQ 1

**I'm test compiling code within CodeSnip and get compiler warnings I don't want. Can I switch them off?**

If you're using CodeSnip with Delphi 6 or later the answer is "Yes".

Use the ***Tools | Preferences*** menu option to display the ***Preferences*** dialogue box and select the ***Code Generation*** tab. Check the *Emit $WARN directives* check box. This will cause compiler directives to be emitted to switch on and off certain warnings. To switch a given warning off, find it in the list box, select it and set it's ***Warning State*** radio button to *off*.

If the symbol you require is not listed you can add it. If you do this make sure you select the correct version of the compiler where the directives were introduced to hide them from earlier compilers, otherwise compilation with the earlier compilers will fail.

Click the dialogue box's ***Help*** button to get more detailed information on how to do this.

## FAQ 2

**Why can't I edit snippets from the on-line database?**

Snippets downloaded from the on-line database are read-only. If you could edit them any changes would be lost the next time you updated the database. This is because the updater overwrites all local copies of snippets with those it downloads.

However, you *can* create a user defined snippet with the same name as one from the on-line database and copy the source code of the read only snippet into it.

The easiest way to do this is to make duplicate snippets easily by using the ***Snippets | Duplicate Snippet*** menu option or by pressing `Shift+Ctrl+D`.

## FAQ 3

**What changes does CodeSnip make to my system?**

Full details of changes are given in the program's ReadMe file, `ReadMe.txt`. Any changes will be recorded there first, but here's a summary.

There are two editions of CodeSnip 4: standard and portable. You can tell the difference by looking at the main window caption. The caption of the portable edition includes the word "Portable"!

The portable edition makes no changes to the host operating system - it writes all its configuration data is written into the folder from which it is run.

The standard edition makes the following changes to the host system:

* The main program's executable file and documentation are installed into the chosen install folder (the `%ProgramFiles%\DelphiDabbler\CodeSnip-4` folder by default).

* Files required by the uninstaller are stored in the main installation's `Uninst` sub-folder.

* The program's uninstall information is registered with the ***Add / Remove Programs*** (a.k.a ***Programs and Features***) control panel applet (information is stored in the registry).

* A program group may be created in the start menu (optional).

* A `%ProgramData%\DelphiDabbler\CodeSnip.4` folder is created. A configuration file is stored in the folder. Once the database is downloaded, its files will be stored in a `Database` sub-folder (see below).

* A `%AppData%\DelphiDabbler\CodeSnip.4` folder is also created. This is used to hold a file that stores per-user configuration data. A `UserDatabase` sub-folder is used to store any user defined snippets. **Note:** From CodeSnip 4.3.0 the user can change the directory containing the user-defined snippets.

## FAQ 4

**What personal information is stored by CodeSnip?**

See the program's privacy statement for details. This can be displayed by starting CodeSnip and selecting the ***Help | Privacy Statement*** menu option. There's also a file called `Privacy.txt` installed with CodeSnip with identical content to the help file topic.

Different versions of CodeSnip may have different privacy statements.

## FAQ 5

**How do I get CodeSnip to use a proxy server to access the internet?**

Start CodeSnip then do the following:

* Select the ***Tools | Proxy Server*** menu option to display the ***Proxy Server Configuration*** dialogue box.
* Tick the ***Use proxy server*** check box.
* Enter the proxy server's IP address and the port number you use to access it in the first two edit boxes. These entries are compulsory.
If you use a user name and password to access the proxy server enter them in the next two edit boxes and confirm the password in the last edit box.
* Click the ***OK*** button and you're done.

CodeSnip will now use the proxy server each time it accesses the internet directly. If there's problem check you have entered valid information in the dialogue box.

>  **Note:** The proxy information entered here is not used when CodeSnip displays a web page using the default web browser - the browser's own proxy setting will be used in this case.

You can temporarily disable proxy access by un-ticking the ***Use proxy server*** check box and clicking ***OK***. Re-enable it when you like by ticking the check box again: CodeSnip will remember the previous data.

Your password is stored in CodeSnip's config file in encrypted form. 

> **WARNING: You must remember your proxy password it because CodeSnip *is not able* remind you of it.**

## FAQ 6

**How do I cross-reference my snippets using the "See also" field?**

You may have noticed that snippets downloaded from the online database display clickable cross references in the ***See also*** field in the main display. You can give your own snippets cross references. To do this:

* Select the required snippet. This must be one of your own user-defined snippets.
* Display the snippet in the ***Snippets Editor*** by choosing the ***Database | Edit Snippet*** menu option or by pressing `Ctrl+F2`.
* Select the ***References*** tab in the ***Snippets Editor***.
* Choose the snippets you want to cross-reference from the ***Cross-references*** check list box. You can choose as many as you like.
* Click ***OK***.

The chosen snippets will now be displayed in the main window's ***See also*** section. Clicking any of the snippets listed there will cause that snippet to be displayed.

If you delete a user defined snippet that is cross referenced by one or more other snippets the deleted snippet will be removed from their ***See also*** fields.

Note that you can't edit the cross-references for snippets from the online database - [FAQ 2](#faq-2) explains why not.

## FAQ 7

**Delphi XE2 generates a "F1026 File not Found ?????.dcu" error when test compiling snippets. What's going wrong?**

> **Note:** This FAQ applies equally well to Delphi XE3 to Delphi 10 Seattle. Whenever "XE2" is mentioned, read "XE3", "XE4", "XE5", "XE6", "XE7", "XE8" or "10 Seattle" as appropriate.

This error is caused when Delphi XE2 can't find one of the RTL or VCL units referenced by the snippet being compiled.

XE2 organises most of these units into "namespaces", meaning that the unit names must be qualified by prepending the name of the namespace. For example `SysUtils` belongs to the `System` namespace and its fully qualified name is `System.SysUtils`.

The problem arises because CodeSnip does not use fully qualified unit names when test compiling. This is for reasons of backward compatibility with older versions of Delphi.

However, Delphi XE2 provides a command line option that lets you specify a list of namespaces to be searched when it encounters unqualified unit names. This is the `-NS` option. You append a semi-colon separated list of namespaces to be searched to the command, for example: `-NSSystem;Vcl;Vcl.Bind`

You need to get CodeSnip to pass this parameter to the compiler. The method depends on the version of CodeSnip you are using.

### CodeSnip v4.3 and later

* Display the ***Configure Compilers*** dialogue box from the ***Tools | Configure Compilers*** menu option.
* Select the Delphi XE2 compiler from the scrolling list on the left hand side of the dialogue box.
* Select the ***Namespaces*** tab.
* Add each of the required namespaces in turn by entering them in the edit box and pressing the ***Add*** button. You can also press the ***Default*** button to provide a set of default namespaces that contain the most commonly used units. This list can be added to.
* Click ***OK*** to update the compiler options.

The next time you test compile a snippet, CodeSnip will generate the required `-NS` option.

#### Earlier versions

* Display the ***Configure Compilers*** dialogue box from the ***Tools | Configure Compilers*** menu option.
* Select the Delphi XE2 compiler from the scrolling list on the left hand side of the dialogue box.
* Select the ***Switches*** tab (named ***Command Line*** on some versions of CodeSnip).
* Check to see if a `-NS` command is already present in the ***Switches*** list. If so, select it.
* In the ***Add or edit switch*** box enter the required `-NS` command (or modify any existing command you selected in step 3). For example if your snippet uses `SysUtils` and `Windows` enter `-NSSystem;WinAPI`.
* If you are adding a new `-NS` command click the ***Add*** button to add the command to the ***Switches*** list. If you are editing an existing command click ***Replace*** instead.
* Click ***OK*** to update the compiler options.

From time to time you may need to add another namespace. Just repeat the appropriate process above and add the necessary namespace(s).

You can see a list of RTL and VCL namespaces, and the units they contain, in the Delphi XE2 or later help. The current list is in the [*Unit Scope Names*](http://docwiki.embarcadero.com/RADStudio/Rio/en/Unit_Scope_Names) topic of the RADStudio documentation.

At the time of writing, the following namespaces are required to compile all the code in the online Code Snippets Database:

* `System`
* `Vcl`
* `Winapi`
* `Vcl.Imaging`
* `System.Win`

> Thanks to [geoffsmith82](https://sourceforge.net/u/geoffsmith82/profile/) for finding the cause of this problem.
