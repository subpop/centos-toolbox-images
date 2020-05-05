This is a CentOS container meant for use with toolbox.

To use the image with toolbox, you must build it with a tag:

`podman build . -t centos-toolbox:8`

Then set up a toolbox container:

`toolbox create --container centos-8 --image centos-toolbox:8`
