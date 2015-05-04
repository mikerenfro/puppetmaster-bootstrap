Mike Renfro's shell script and supporting files to bootstrap a puppetmaster on a new Debian, Ubuntu, CentOS (and possibly RHEL) install.
Currently uses:

  * Debian/Ubuntu puppet and puppetmaster-passenger packages from apt.puppetlabs.com,
  * CentOS/RHEL puppet and puppet-server packages from yum.puppetlabs.com, plus Rack and Passenger gems
  * puppetdb module from puppetforge for Postgresql and storeconfigs

All modules, manifests, and other content is stored in environment directories, rather in top-level /etc/puppet directories.
This should make it easier to merge code changes among dev, testing, and production environments as appropriate.

To keep this structure intact, any calls to `puppet module install` need to have additional arguments of `--environment ${env} --modulepath /etc/puppet/environments/${env}/modules`, replacing `${env}` with the actual environment name.

# Pre-installation

CentOS and RHEL use SELinux by default. Loosen up its default settings by setting `SELINUX=permissive` in `/etc/selinux/config` and rebooting.
Forks and pull requests that can fix this will be greatly appreciated.

# Download

- Debian/Ubuntu: `wget -O puppetmaster-bootstrap.tgz https://github.com/mikerenfro/puppetmaster-bootstrap/tarball/multi-os`

- CentOS/RHEL: `curl -L -o puppetmaster-bootstrap.tgz https://github.com/mikerenfro/puppetmaster-bootstrap/tarball/multi-os`

# Installation

1. `tar --strip-components=1 -zxvpf puppetmaster-bootstrap.tgz`
2. `./bootstrap`
