
#Installation
* Install [IntelliJ IDEA](https://www.jetbrains.com/idea/) from JetBrains site (you may also use other JB IDE).
* Go to Settings->Plugins->Browse repository and install Camelcade plugin
* Restart IDEA

# Creating and configuring project
Choose File->New->Project:

![Creating new project](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/createproject.png)

Open project structure:

![Opening Project structure](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/projectstructure.png)

Goto Platform Settings->SDK and choose add Perl Interpreter:

![Add Perl5 interpreter into IDEA](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/sdktype.png)

If everything went right, you'll see Perl interpreter string and class-paths will be filled with @INC paths:

![Added Perl5 interpreter](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/sdkadded.png)

If paths were not added automatically, you may add them manually. Don't forget to report the problem into our issue tracker (specify IDE name and version and OS).

After that, go to Project tab and choose added Perl Interpreter there:

![Choosing project SDK](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/projectsdk.png)

#Creating and configuring a module

![Adding a module](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/newmodulestart.png)

![Choosing module type](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/newmoduletype.png)

![Choosing module name and paths](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/newmoduledialog.png)

![Choosing module SDK](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/newmodulesdk.png)

![Properly created module](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/createdmodule.png)

![Marking directories as source, tests. Excluding some of them.](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/marksources.png)

![Adding project's lib directory](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/addlibdir.png)

![Choosing lib directory type](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/chooselibtype.png)

![Moving library up into resolution order](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/movelibup.png)


![Configured project](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/finalstep.png)