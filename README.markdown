Mike Renfro's shell script and supporting files to bootstrap a
puppetmaster on a new Debian install. Currently uses:

  * puppet packages from apt.puppetlabs.com
  * nginx-light 1.1.14 (from Debian backports)
  * mysql 5.1 for storeconfigs

Installation:

  1. mkdir (target); cd (target)
  2. wget -O puppetmaster-bootstrap.tgz https://github.com/mikerenfro/puppetmaster-bootstrap/tarball/master
  3. tar --strip-components=1 -zxvpf puppetmaster-bootstrap.tgz 
  4. ./bootstrap
