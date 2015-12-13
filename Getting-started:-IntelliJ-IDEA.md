#Installation
* Install [IntelliJ IDEA](https://www.jetbrains.com/idea/)
* Start IDEA and go to the `File -> Settings -> Plugins -> Browse repository` and install Camelcade plugin
* Restart IDEA
* Before starting, please, check out the list of [implemented features](https://github.com/hurricup/Perl5-IDEA/wiki/Implemented-features) and [known issues](https://github.com/hurricup/Perl5-IDEA/wiki/Known-issues).

# Creating and configuring project
Choose `File -> New -> Project`:

![Creating new project](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/createproject.png)

Open project structure:

![Opening Project structure](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/projectstructure.png)

Goto `Platform Settings -> SDK` and choose add Perl Interpreter:

![Add Perl5 interpreter into IDEA](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/sdktype.png)

In opened directory choosing dialog you should select a bin directory where perl executable is located. Usually, this directory is already selected in opened dialog. Click Ok.

If everything went right, you'll see Perl interpreter string and classpaths will be filled with Perl's `@INC` paths:

![Added Perl5 interpreter](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/sdkadded.png)

If paths were not added automatically, you may add them manually. Don't forget to report the problem into our issue tracker (specify IDE name, version and your OS).

After that, go to `Project` tab and choose added Perl Interpreter there:

![Choosing project SDK](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/projectsdk.png)

#Creating and configuring a module

Go to Modules tab and choose `Add: New Module`:

![Adding a module](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/newmodulestart.png)

In opened dialog choose `Perl5 module`:

![Choosing module type](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/newmoduletype.png)

Type module name, choose content root and module file (iml) location:

![Choosing module name and paths](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/newmoduledialog.png)

Choose added Perl Interpreter:

![Choosing module SDK](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/newmodulesdk.png)

If you've done everything right, you'll see something like this:

![Properly created module](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/createdmodule.png)

Here you may mark directories of your module as Sources and Tests. Also you may Exclude some directories to avoid searching sources in there:

![Marking directories as source, tests. Excluding some of them.](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/marksources.png)

To let Camelcade search for package files, you should mark your lib directory as a library source (what you are doing with -I parameter of Perl interpreter). 

Remember, all packages being resolved relatively to one of the lib dirs: module or SDK-specific.

#How should it look like

If everything was done right, you'll see a similar picture:
* You module 
* Colorized directories of your module (depending on type)
* Your lib directory will have annotation `library home`

![Configured project](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/finalstep.png)

Enjoy!