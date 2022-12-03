# Build & Install on Fedora 37

## Get the code

```sh
# Plain ST experimental repository with a few build patches
git clone --depth 1 "https://github.com/mara004/scantailor.git"
git remote set-branches origin '*'
git fetch -v --depth=1
git checkout build-experimental
```

## Install Dependencies

Notes:
* Probably includes some unnecessary dependencies
* Not sure how to build with OpenCL support

```sh
sudo dnf install cmake boost-devel libpng-devel zlib-devel libjpeg-turbo-devel libtiff-devel eigen3-devel qt5-qtbase-devel qt5-qtsvg-devel qt5-qttools-devel
```

## Build

```sh
cmake .. -DOpenGL_GL_PREFERENCE=GLVND
make -j$(nproc)
```
