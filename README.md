# Docker image with rpmbuild environment and Go installed

Base system:

* Amazon Linux 2: `Dockerfile.amazonlinux2`

## Build

* Default Go version (1.20.1): `docker build -f Dockerfile -t gorpmbuild:latest .`
* Specific Go version: `docker build --build-arg "GO_VERSION=1.19.1" -f Dockerfile -t gorpmbuild:latest .`

## Usage

* Build everything, rpm files will be placed in RPMS/ and source rpm files in SRPMS/: `docker run --rm -it --volume ${PWD}:/build/rpm gorpmbuild:latest -ba build/project.spec`
* Build rpm files only: `docker run --rm -it --volume ${PWD}:/build/rpm gorpmbuild:latest -bb build/project.spec`
