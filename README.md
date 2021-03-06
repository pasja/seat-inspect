# seat-inspect

seat-inspect tries to make the status of the login/seat system visible, to help
with understanding and troubleshooting.

The intent of running the code is to have an overview of the system status, both
to see what the new facilities are about, and to figure out if there is
something out of place.

The intent of reading the code is to have an idea of how to use these
facilities: the code has been written to be straightforward and is annotated
with relevant bits from the [logind API documentation](http://www.freedesktop.org/wiki/Software/systemd/logind/).

See also [here](http://www.freedesktop.org/wiki/Software/systemd/multiseat/)
for general definitions.

seat-inspect is not a finished tool, but a starting point. I put it on github
hoping that people will fork it and add their own extra sanity checks and
warnings, so that it can grow into a standard thing to run if a system acts
weird.

As it is now, it should be able to issue warnings if some bits are missing for
network-manager or shutdown functions to work correctly. I haven't really
tested that, though, because I don't have a system at hand where they are
currently not working fine.

Another nice thing of it is that when running `seat-inspect -v` you get a dump
of what logind/consolekit think about your system. I found it an interesting
way to explore the new functionalities that we recently grew. The same can be
done, and in more details, with `loginctl` calls, but I lacked a summary.
