Since [version 2018.3](https://github.com/Camelcade/Perl5-IDEA/releases/tag/2018.3) Windows users may use a Perl interpreter from 
[Windows Subsystem For Linux](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux).

Plugin provides you a possibility to add and work with fully-functional Perl interpreter from your WSL linux environment, including Perl5 
from supported version managers: [Plenv](https://github.com/Camelcade/Perl5-IDEA/wiki/Plenv-support) or [Perlbrew](https://github.com/Camelcade/Perl5-IDEA/wiki/Perlbrew-support). 

IDE treats WSL as a remote machine and downloads files from `@INC` directories to the local cache for indexing. If you have installed something
manually, using console outside of IDE, don't forget to use `Refresh Interpreter Information` action from `Tools: Perl5` menu. 
This action updates local cache files. 

**IMPORTANT**: Project files for execution used directly, via WSL mount points, e.g. `/mnt/c` for `C:\`. Any changes done to the project files inside the 
WSL in runtime are done to the real host machine files. 

WSL support available with a [separate plugin](https://plugins.jetbrains.com/plugin/11329), available for professional versions of IDEs.

