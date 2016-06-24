Don't judge this set of fugly scripts too harsh. They're very useful!

rpmResolver takes a name of a package (my understanding is that the package has to be already installed on the system) and works out a space-separated list of its dependencies. This script is ripped off Jeff Johnson's [SO answer](http://stackoverflow.com/questions/37927066/collect-all-rpm-dependencies-to-deploy-a-project).

rpmDownloader takes a name of a package, resolves its dependencies using rpmResolver and then downloads all dependent packages using dnf. One thing I noticed is that the dependencies might be quite heavy. A hello world website written in go actually depends on 150 MB of packages, so you probably don't want to deploy go websites using this approach (A single go binary will rarely weight more than 30 MB!)

I plan to implement a script to scp these rpms onto a machine and install them there, which hopefully will mean that the application works on the deployed system (there's a warning about this in the linked SO answer).

Happy deployments!

