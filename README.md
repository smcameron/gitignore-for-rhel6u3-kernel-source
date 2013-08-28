gitignore-for-rhel6u3-kernel-source
===================================

.gitignore file for rhel6u3 kernel source

For some completely insane<sup>1</sup> reason redhat does not ship a gitignore file with
their completely insane<sup>2</sup>kernel source rpms.   So here is my attempt at making
one and storing it here in a place where I can find it later, and where
others might find it as well.

<sup>1</sup> I say "completely insane" because there's no sane reason 
for redhat not to ship a .gitignore, *especially* when they add a million
binary files lying around after the build related to digital signatures that
without a reasonable .gitignore file would get incorporated into patches if
you're using something like stacked git *unless* you expressly intend to
annoy the shit out of developers who are trying to help you.  And I don't
think they mean to do that.

<sup>2</sup>I say "completely insane" because people who download the
kernel source rpms are doing so, surprise surprise, *because they want
the kernel source*.  The kernel source RPM is *distro* and even *version*
specific.  You can't really unpack it in a sane way on any distro other
than the one for which it is intended.  So, just to *look* at the source,
you need to rummage around and find a machine that has the correct OS
installed on it so you can do:

    rpm -ihv kernel-blah-src.rpm
    cd rpmbuild/SPECS
    rpmbuild -bp kernel.spec
    cd ../BUILD/kernel*
    mv linux-* ~

And that's *after* you've installed the myriad other rpms which the
kernel source rpm build process depends on.

In what way is this better than a tarball?  I'll tell you:  It is in *no way*
better than a tarball.


    



