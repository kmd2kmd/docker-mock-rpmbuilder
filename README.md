# docker-mock-rpmbuilder

Build RPMs from rpmbuild/SPECS or rpmbuild/SOURCES with mock, clean room builder for RedHat Enterprise Linxu derivative distributions.

## Build Docker Image

```console
$ docker build -t mock-rpmbuilder .
```

## Examples to build RPM packages

To rebuild packages from `*.src.rpms` under the `/path/to/rpmbuild/SRPMS/` for `epel-6-x86_64` environment.

```console
$ docker run -e MOCK_CONFIG=epel-6-x86_64 -e MOCK_TARGET=SRPMS -v /path/to/rpmbuild:rpmbuild --privileged=true -it mock-rpmbuilder
```

To build packages from `*.spec` under the `/path/to/rpmbuild/SPECS/` for `epel-6-x86_64` environment.

```console
$ docker run -e MOCK_CONFIG=epel-6-x86_64 -e MOCK_TARGET=SPECS -v /path/to/rpmbuild:rpmbuild --privileged=true -it mock-rpmbuilder
```

## License

Dockerfile and build scripts is dedicated to 
[![CC0](http://i.creativecommons.org/p/zero/1.0/80x15.png "CC0")](https://creativecommons.org/publicdomain/zero/1.0/).
No rights reserved.

License for distributed Docker images follows one of [Fedora Project](https://fedoraproject.org) and installed packages.