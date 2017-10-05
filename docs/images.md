
## Custom Images

By default, Cloudbreak launches clusters from an image that includes default configuration and default tooling for provisioning. These are considered the Standard default images and these images.

In some cases, these default images might not fit the requirements of users: for example when they need custom OS hardening, libraries, tooling, and so on. In such cases, the user would like to start their clusters from their own custom image.

### Building Custom Images

Refer to [Custom Images for Cloudbreak](https://github.com/hortonworks/cloudbreak-images). This repository includes instructions and scripts to help you build custom images. Once you have the images, refer to the documentation below for information on how to register and use these images with Cloudbreak.

### Registering Custom Images

Register your custom image(s) in Cloudbreak by placing `yml` files that declare your custom images in the `/var/lib/cloudbreak-deployment/etc` directory on the Cloudbreak host. The `etc` directory does not exist by default, so you need to create it.

The format of the `yml` files is cloud provider specific and described in the following sections.  

> If you register the images after Cloudbreak has been started, you need to restart Cloudbreak after updating the images.

#### Register Images for AWS

To override the default images, create the following file: `/var/lib/cloudbreak-deployment/etc/aws-images.yml` and update its content by replacing the images listed with your custom image for each region that you want to use. The default content of the `yml` file is:

<pre>
aws:
  ap-northeast-1: ami-76729917
  ap-northeast-2: ami-7c1ad112
  ap-southeast-1: ami-a7ac7fc4
  ap-southeast-2: ami-acf7decf
  eu-central-1: ami-71da331e
  eu-west-1: ami-cba43bb8
  sa-east-1: ami-f8901a94
  us-east-1: ami-48ba9d5e
  us-west-1: ami-b76421d7
  us-west-2: ami-d541bbb5
</pre>

#### Register Images for Azure

To override the default images, create the following file: `/var/lib/cloudbreak-deployment/etc/arm-images.yml` and update its content by replacing the images listed with your custom image for each region that you want to use. The default content of the `yml` file is:

```
azure_rm:
  East Asia: https://sequenceiqeastasia2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  East US: https://sequenceiqeastus2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  Central US: https://sequenceiqcentralus2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  North Europe: https://sequenceiqnortheurope2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  South Central US: https://sequenceiqouthcentralus2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  North Central US: https://sequenceiqorthcentralus2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  East US 2: https://sequenceiqeastus22.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  Japan East: https://sequenceiqjapaneast2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  Japan West: https://sequenceiqjapanwest2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  Southeast Asia: https://sequenceiqsoutheastasia2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  West US: https://sequenceiqwestus2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  West Europe: https://sequenceiqwesteurope2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
  Brazil South: https://sequenceiqbrazilsouth2.blob.core.windows.net/images/cb-2016-06-14-03-27.vhd
```

#### Register Images for GCP

To override the default images, create the following file: `/var/lib/cloudbreak-deployment/etc/gcp-images.yml` and update its content by replacing the images listed with your custom image for each region that you want to use. It is not required to have an image in every region, as the `default` is used everywhere. The default content of the `yml` file is:

<pre>
gcp:
  default: sequenceiqimage/cb-2016-06-14-03-27.tar.gz
</pre>

#### Register Images for OpenStack

To override the default images, create the following file: `/var/lib/cloudbreak-deployment/etc/os-images.yml` and update its content by replacing the images listed with your custom image for each region that you want to use. It is not required to have an image in every region, as the `default` is used everywhere. The default content of the `yml` file is:

<pre>
openstack:
  default: cloudbreak-2016-06-14-10-58
</pre>