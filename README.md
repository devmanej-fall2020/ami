# Creation of an Amazon Machine Image using Packer

Instructions for using Packer:

Packer is an open source tool for creating identical machine images for multiple platforms from a single source configuration. Packer is lightweight, runs on every major operating system, and is highly performant, creating machine images for multiple platforms in parallel. When building images, Packer is able to use tools like Chef or Puppet to install software onto the image.

A machine image is a single static unit that contains a pre-configured operating system and installed software which is used to quickly create new running machines.Machine image formats change for each platform. Some examples include AMIs for EC2, VMDK/VMX files for VMware, OVF exports for VirtualBox.

It does that by preloading all needed software and configuration on an EC2 instance, then creating an image of that. The resulting image can then be used to launch new instances with all software and configuration pre-loaded. This process allows the EC2 instance to come online and be available quickly. It not only simplifies deployment of new instances but is especially useful when an instance is part of an Auto Scaling group and is responding to a spike in load. If the instance takes too long to be ready, it defeats the purpose of dynamic scaling.

This project focusses on the Amazon Web Services cloud platform, but the steps will be quite similar for itself cloud providers as well. Please refer to you product documentation for more information. 

Prerequisites: 
The following are the prerequisites for running this application
1. AWS Account
2. Packer

Contents:
1. packer-template.json - This file contains the template on which packer builds the new AMI.
2. packer-vars.json - This file contains the variable values that would be required for packer to run.


The steps for using packer are:
1. Identify the source AMI image that you would like your new image to be based on.
2. Identify the target software configuration that you would like to present in the newly created image, and note them. They are to be included in the image.
3. Specify all details in the template file according to documentation provided by Hashicorp.
4. Run the command packer build. In this repo, since automation is used, the build process will be initialised on merging with main branch.