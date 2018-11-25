Since [version 2018.3](https://github.com/Camelcade/Perl5-IDEA/releases/tag/2018.3) it's possible to use Perl5 interpreter
from the [Docker container](https://www.docker.com/)

Plugin provides you a possibility to add and work with fully-functional Perl5 interpreter from the Docker image of your choice, including Perl5 
from supported version managers: [Plenv](https://github.com/Camelcade/Perl5-IDEA/wiki/Plenv-support) or [Perlbrew](https://github.com/Camelcade/Perl5-IDEA/wiki/Perlbrew-support). 

For each execution of your script, or tool, like `perlcritic` or `pertidy`, IDE creates a new container, executes command and removes container.

Meaning you can't, for example, install any packages into such interpreter with IDE actions, as you may do in local case. Current workflow
expects that docker image you are using is properly built and any persistent updates should be done using `Dockerfile` and image re-building.

IDE treats container as a remote machine and downloads files from `@INC` directories to the local cache for indexing. If you have rebuilt 
your docker image, e.g. to install some packages, don't forget to use `Refresh Interpreter Information` action from `Tools: Perl5` menu. 
This action updates local cache files. 

**IMPORTANT**: Every container has a `/intellijperl` mount point in your root filesystem. This mount point contains your host machine files: your project,
some helpers scripts and IDE internal files. Any changes inside this mount point are changes to your host machine filesystem, not container.

Docker support available with a [separate plugin](https://plugins.jetbrains.com/plugin/11328), available for professional versions of IDEs.
