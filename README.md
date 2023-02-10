# Debian Packaging for prometheus-flask-exporter for Wazo

This repository contains the packaging information for
[python-prometheus-flask-exporter](https://github.com/rycus86/prometheus_flask_exporter).

## Building a new version

To build a new version of python-prometheus-flask-exporter for Wazo.

* Update the version number in the `VERSION` file
* Update the changelog using `dch -i` to the matching version
* Push the changes

[Jenkins](https://jenkins.wazo.community) will then retrieve and build the new version.

## Building Locally

The following procedure can be used to build on a test environment before submitting a change.

```sh
make -f debian/rules get-orig-source
tar -xvf ../wazo-python-prometheus-flask-exporter-packaging_*.orig.tar.gz  --strip 1
dpkg-buildpackage -us -uc
```

The `.deb` will be located in the parent directory.
