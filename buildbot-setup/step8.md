So it is time to modify the "master.cfg". If you open it up in the editor, you will see that it has quite detailed information about what everything is and how it is used. 
For example, the creation on workers such as the "example-worker" made to deal with the "runtests" you tried earlier. You can think of them as the ones executing the intructions you've 
configured to be executed in the "master.cfg". In this tutorial it is however not necessary to modify the workers. If you do want information about modifying the workers please check out 
the [Worker documentation](https://docs.buildbot.net/latest/manual/configuration/workers.html)

Moving on to something more functional, the category of "#CHANGESOURCES" deals with where BuildBot should look to find any source code changes in a version control system. Such as when a push is made to a Git repository.
In our case a GitPoller is used. There are more types of repositories than ones using Git so if you want more information about those checkout [this documentation](https://docs.buildbot.net/latest/manual/configuration/changesources.html).
We are going to change the value `git://github.com/buildbot/pyflakes.git` to the value `INSERT NEW GIT HERE`. So now, if any changes were made to this Git repository while this BuildBut was running, it would perform "runtests". 

We then move on to the Builders category, [INSERT MORE INFORMATION HERE ABOUT BUILDERS] in particular it is interesting to look at the BuildFactory and the steps added to it. 
The first steps sets a repository to collect and the second states that a command should be executed.
So if you want to use a personal repository, you would have to replace the information `repourl='http://github.com/buildbot/pyflakes.git'` with something like `repourl='http://github.com/YOURUSERNAME/YOURREPOSITORY.git'`.
If this does not satisfy your curiosity about Builders or BuildFactories please checkout the [Builders documentation](https://docs.buildbot.net/latest/manual/configuration/builders.html) 
or the [BuildFactory documentaiton](https://docs.buildbot.net/latest/manual/configuration/buildfactories.html).

In our case, we're going to replace the repository URL `http://github.com/buildbot/pyflakes.git`with the URL `INSERT GIT URL HERE`. Then we are going to change the command execution in the second step from 
`command=["trial", "pyflakes"])` to `command=["python", "INSERT FILE NAME HERE"])`.

Congratulations, you've now successfully ran BuildBot's Docker image, and you've reconfigured it to utilise a different Git repository. 

Please move on to the next step.
