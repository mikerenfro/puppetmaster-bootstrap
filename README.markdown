Mike Renfro's shell script and supporting files to bootstrap a
puppetmaster on a new Debian install. Currently uses:

  * puppet and puppetmaster-passenger packages from apt.puppetlabs.com
  * puppetdb module from puppetforge for Postgresql and storeconfigs

All modules, manifests, and other content is stored in environment
directories, rather in top-level /etc/puppet directories. This should
make it easier to merge code changes among dev, testing, and production
environments as appropriate.

To keep this structure intact, any calls to `puppet module install`
need to have additional arguments of
`--environment ${env} --modulepath /etc/puppet/environments/${env}/modules`,
replacing `${env}` with the actual environment name.

Installation:

  1. mkdir (target); cd (target)
  2. wget -O puppetmaster-bootstrap.tgz https://github.com/mikerenfro/puppetmaster-bootstrap/tarball/master
  3. tar --strip-components=1 -zxvpf puppetmaster-bootstrap.tgz 
  4. ./bootstrap
