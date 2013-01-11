Mike Renfro's shell script and supporting files to bootstrap a
puppetmaster on a new Debian install. Currently uses:

  * puppet, puppetmaster-passenger, and puppetdb packages from apt.puppetlabs.com
  * postgres for storeconfigs

Installation:

  1. mkdir (target); cd (target)
  2. wget -O puppetmaster-bootstrap.tgz https://github.com/mikerenfro/puppetmaster-bootstrap/tarball/master
  3. tar --strip-components=1 -zxvpf puppetmaster-bootstrap.tgz 
  4. ./bootstrap
