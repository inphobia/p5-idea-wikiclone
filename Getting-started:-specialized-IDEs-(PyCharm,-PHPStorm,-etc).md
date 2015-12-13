#Installation
* Install your IDE from the [JetBrains website](https://www.jetbrains.com/)
* Start IDE and go to `File -> Settings -> Plugins -> Browse repository` and install Camelcade plugin
* Restart IDE
* Before starting, please, check out the list of [implemented features](https://github.com/hurricup/Perl5-IDEA/wiki/Implemented-features) and [known issues](https://github.com/hurricup/Perl5-IDEA/wiki/Known-issues).

#Selecting interpreter
In order to properly resolve installed packages, you should select Perl interperter. This can be done in `File -> Settings -> Languages & Frameworks -> Perl5 settings`. NB: env is not supported. It should be direct path.

![Selecting Perl5 interpreter](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted_microide/selectinterpreter.png)

#Marking libraries
In order to properly resolve projects libraries, you should mark lib directories (same as you pass into the -I key). This can be done in `File -> Settings -> Project -> Perl5 libs`:

![Marking Perl5 libraries](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted_microide/marklibraries.png)

#How should it look like

If everything was done right, you'll see a similar picture:
* Colorized directories of your module (depending on type)
* Your lib directory should be purple
* Perl5 libraries should be listed in External Libraries

![Configured project](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted_microide/finalstep.png)

Enjoy!