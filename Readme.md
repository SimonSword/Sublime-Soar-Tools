============
Sublime Text Soar Tools
============

Sublime Text package for [Soar](http://sitemaker.umich.edu/soar/home) development. Currently only tested for Sublime Text 3.

Getting Started
===============

* After installing [Package Control](https://sublime.wbond.net/installation), use the *Command Palette* (``Ctrl+Shift+P``) to select
   ``Install Package`` and then search for ``Soar Tools``.
<!-- * Access commands from **Tools | Packages | Package Development** or the *Command Palette*. -->

Current Functionality
=====================

###SoarUnit

If you have [JSoar/SoarUnit](https://code.google.com/p/jsoar/wiki/SoarUnit) on your computer, you can run it with a build command (ctrl+b or command+b) when you have a SoarUnit file open. You will, however, need to specify the location of SoarUnit if it is not in your PATH. You may also wish to test using C Soar. To specify these settings, go to Preferences --> Package Settings --> Soar-Tools --> Settings - User. These are your available settings:

    {
        // If added to your system path, "soarunit" is fine; otherwise,
        // you'll need to set this to "C:/jsoar-0.14.0/bin/soarunit", etc.
        // in the user settings.
        "soarunit_path": "soarunit",

        // set to true if you want to use C Soar, not JSoar
        "c_soar": false,

        // If using C Soar, set this to the Soar distribution directory, or set
        // the SOAR_HOME environment variable
        // "SOAR_HOME": "C:/path/to/soar-9.x.x",

        // set to true if you want a pretty popup window instead of console
        // output
        "ui": false,

        // indicate the size of thread pool to run tests in;
        // either a number indicating the fixed size of a thread pool,
        // "cpus" for number of cpus, or "cached" for cached
        "threads": "cpus"
    }

You can either run SoarUnit on the current file, or for the whole project, but the project option is currently slow and buggy, and therefore not recommended.

###Syntax Highlighting

Soar syntax highlighting is applied to files with the '.soar' or '.soarunit' extensions. Code folding is also provided but is irregular at the moment.

###Snippets

Several snippets are currently provided for various types of Soar productions, [SoarDoc](http://web.eecs.umich.edu/~soar/sitemaker/projects/soardoc/soardoc.html), and [SoarUnit](https://code.google.com/p/jsoar/wiki/SoarUnit) setup/test blocks. SoarDoc snippets are triggered by `##!` and production snippets are triggered by `sp`. Provided snippets are:

* SoarDoc, triggered by `##!`, for:
    - documenting a file
    - documenting an operator
    - documenting a production
* Soar productions, triggered by `sp`, for:
    - propose/compare/apply operator
    - elaborate state
    - elaborate substate
* SoarUnit blocks:
    - setup block
    - test block

###SublimeREPL Integration
You can run the Soar CLI from SublimeText if you have the [SublimeREPL](https://github.com/wuub/SublimeREPL) package installed. 

* You may need to change the configuration so that SublimeREPL can find the CLI executable on your machine. This configuration is located in `path/to/packages/Sublime-Tools/Main.sublime-menu`. You need to change this line:

    "cmd": ["%SOAR_HOME/bin/cli.exe"],

The default value is a Windows-style path and also assumes that the `SOAR_HOME` variable is set on your machine. So if you are on Linux or do not have that environment variable set, you need to edit the path to point to the Soar cli on your machine.

* Keep in mind that the Soar Tutorial distribution does not currently come with the CLI executable, so you need to the normal distribution to use SublimeREPL with Soar.

###TODO

* Make it work on ST2
* Solicit feedback from Soar users
