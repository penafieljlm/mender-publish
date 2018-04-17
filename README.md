# mender-scripts
Simple shell scripts which you can use to manage your mender server.

## Requirements
The scripts require the following applications to be installed:
* bash
* curl
* python

In your Yocto project root, ensure that your build environment is initialized:
```
user@yocto:~/poky$ source oe-init-build-env <build-directory>
```

And in your `conf/local.conf` file, ensure that the `MENDER_SERVER_URL` is set to the correct location:
```
MENDER_SERVER_URL = "https://hosted.mender.io"
```

## Scripts

This section contains the selection of the scripts that are available in this project.

### `mender-deployments-post`

Uploads a mender artifact to the backend.

When using the mender-deployments-post utility, it is assumed that you have already generated a `.mender` file. The `mender-deployments-post` script will select the latest artifact based on the provided image.

#### Usage
```
user@yocto:~/poky/build$ mender-deployments-post <image-name> <artifact-description>
```

#### Example
```
user@yocto:~/poky/build$ mender-deployments-post core-image-base "release-1"
```

### `mender-inventory-delete`

Deletes a device from the inventory.

#### Usage
```
user@yocto:~/poky/build$ mender-inventory-delete <device-id>
```

#### Example
```
user@yocto:~/poky/build$ mender-inventory-delete "5ad5c95bfaead6000167662e"
```
