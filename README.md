# mender-publish
A simple script which allows you to publish your Mender artifacts from the console.

## Requirements
The `mender-publish` script requires the following applications to be installed:
* bash
* curl
* python

## Usage
In your Yocto project root, ensure that your build environment is initialized:
```
user@yocto:~/poky$ source oe-init-build-env <build-directory>
```

By this point, it is assumed that you have already generated a `.mender` file. All you have to do now is to invoke the `mender-publish` script:
```
user@yocto:~/poky/build$ mender-publish <image-name> <artifact-description>
```

The `mender-publish` script will select the latest artifact based on the provided image.

The script will ask you for your credentials as they are required for publishing artifacts.
