Since [version 2018.3](https://github.com/Camelcade/Perl5-IDEA/releases/tag/2018.3) Windows users may use a Perl interpreter from 
[Windows Subsystem For Linux](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux).

Plugin provides you a possibility to add and work with fully-functional Perl interpreter from your WSL linux environment, including Perl5 
from supported version managers: [Plenv](https://github.com/Camelcade/Perl5-IDEA/wiki/Plenv-support) or [Perlbrew](https://github.com/Camelcade/Perl5-IDEA/wiki/Perlbrew-support). Do note that according to the plenv devs plenv and perlbrew cannot be used together: https://github.com/tokuhirom/plenv#installation

IDE treats WSL as a remote machine and downloads files from `@INC` directories to the local cache for indexing. If you have installed something
manually, using console outside of IDE, don't forget to use `Refresh Interpreter Information` action from `Tools: Perl5` menu. 
This action updates local cache files. 

**IMPORTANT**: Project files for execution used directly, via WSL mount points, e.g. `/mnt/c` for `C:\`. Any changes done to the project files inside the 
WSL in runtime are done to the real host machine files. 

WSL support available with a [separate plugin](https://plugins.jetbrains.com/plugin/11329), available for ultimate versions of IDEs. Don't forget that [Jetbrains](https://www.jetbrains.com/) is open source friendly and can provide a free ultimate intellij license if it's only used for open source & not for profit use.

### quick install guide
#### The following was done on:
* Windows 10 1903 x64
* IntelliJ IDEA 2019.2 EAP (Ultimate Edition) Build #IU-192.4205.45, built on May 24, 2019
  * Runtime version: 11.0.3+12-b248.2 amd64
* Perl5-IDEA 192.4505.45: base perl5 plugin, wsl plugin and template toolkit plugin
* plenv git commit https://github.com/tokuhirom/plenv/commit/5d03b0c3701065a9dc85570f5e8ab1564850cf1e
* plenv Perl-Build plugin git commit https://github.com/tokuhirom/Perl-Build/commit/3ed37c99a471e4cfdf480a268c7a8de4d0daca34
* opensuse leap 15 from the windows store

#### general advise
* don't change your default shell to anything other as bash. i'm sorry zsh lovers (like me), but between env variables & control character escape differences it's just easier to stick with bash and run zsh for interactive use.
* windows builds older as 1903 have a non killable wsl process bug, use 1903 or be prepared to reboot a lot.
* you can use multiple wsl distros if you want without issue. i have opensuse leap 42, opensuse leap 15 & debian all working on the same machine (each with multiple perl versions)
* while there is a [local::lib](https://github.com/miyagawa/plenv-contrib) plugin for plenv, it still won't work (yet). the syntax to use local::lib & plenv differs from regular plenv version switching. even on commandline it's not always succesfull.

#### installing
* basicly you just need to follow the instructions found on the [plenv github site](https://github.com/tokuhirom/plenv#basic-github-checkout)
  * clone the repo: `git clone https://github.com/tokuhirom/plenv.git ~/.plenv`
  * add plenv to your $PATH: `$ echo 'export PATH="$HOME/.plenv/bin:$PATH"' >> ~/.bash_profile`
  * init and autocompletion: `$ echo 'eval "$(plenv init -)"' >> ~/.bash_profile`
  * now just restart your wsl shell
  * install perl-build plugin for plenv: `git clone https://github.com/tokuhirom/Perl-Build.git ~/.plenv/plugins/perl-build/`
 * now you can start installing perl versions:
   * `plenv install 5.26.3`
   * `plenv install 5.28.2`
 * don't forget to install cpanm for each of your perl versions:
   * `plenv global 5.28.2`
   * `plenv install-cpanm`
   * `plenv rehash`
   * `plenv global 5.26.3`
   * `plenv install-cpanm`
   * `plenv rehash`
   
#### setting up intellij
* wsl will only work with the ultimate edition. (you can use cygwin with the community edition but that's a pain)
* make sure you install the perl plugin from this site.
* when that is done go to settings->languages & frameworks->perl5
* click on the cogwheel where it says perl5 interpreter
  * choose wsl
  * select your distribution
  * select plenv
  * select a perl version
* repeat if you want more than 1 perl version configured.
