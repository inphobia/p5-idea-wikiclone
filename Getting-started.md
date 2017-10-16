# Installation
* Install [IntelliJ IDEA](https://www.jetbrains.com/idea/) or other [JetBrains IDE](https://www.jetbrains.com/products.html)
* Start IDE and go to the `File -> Settings -> Plugins -> Browse repository` and install Perl plugin
* Restart IDE
* Before starting, please, check out the list of [implemented features](https://github.com/hurricup/Perl5-IDEA/wiki/Implemented-features) and [known issues](https://github.com/hurricup/Perl5-IDEA/wiki/Known-issues).

# Creating new project
Choose `File -> New -> Project`:

![Creating new project](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/createproject.png)

Or `File -> Open` and choose a directory with your project files:

![Open File or Project](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/openfolder.png)

# Configuring project

Open settings dialog via menu or `Ctrl + Alt + S` hotkey:

![Opening Settings](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/opensettings.png)

Open `Languages & Frameworks -> Perl5`:

![Perl5 Project Settings](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/projectsettings.png)

This is a main Perl5 settings page. Here you may find:
1. Project settings, including interpreter, frameworks settings and a lot of other staff
2. Module settings, see below
3. List of known interpreters on your machine
4. Button to add new interpreter

Click `New...` button. In opened directory choosing dialog you should select a bin directory where perl executable is located. Usually, this directory is already selected in opened dialog. Click Ok. (**Mac users:** due to the bug in Mac UI, you will be able to select files and directories. You must select containing directory, not perl itself. See [#1404](https://github.com/Camelcade/Perl5-IDEA/issues/1404))

# Configuring module 

Now open your module settings:

![Perl5 Module Settings](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/modulesettings.png)

Here you may mark directories of your module as Libraries and framework roots if necessary. Just select a directory and click respective mark button. 

To let Camelcade search for package files, you should mark your lib directory as a `Perl5 libraries` (what you are doing with `-I` parameter of Perl interpreter). 

# How should it look like

![Configured project](https://github.com/hurricup/Perl5-IDEA/blob/master/images/gettingstarted/configuredproject.png)

If everything was done right, you'll see a similar picture:

1. You lib directory with special icon and gray explanation
2. Selected interpreter with default `@INC` directories

Enjoy!