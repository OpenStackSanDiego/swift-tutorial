# swift-tutorial
Using OpenStack Swift Object Store

You've been tasked with making your companies software and documentation available via the Internet. You've decided to put the files onto a OpenStack Swift Object powered cloud. Swift provide a reliable image store with API access to upload, download and manage the content.

<UL>
<LI>Save a copy of these instructions locally so you can upload them onto Swift
<LI>Assign yourself an account from the <A HREF="https://etherpad.openstack.org/p/san-diego-swift">Etherpad</A> https://etherpad.openstack.org/p/san-diego-swift
</UL>

Swift stores files into containers. First step is to create a new container and upload the documentation into the new container. 
<UL>
<LI>Log into <A HREF="https://ca.ovh.com">OVH</A> (https://ca.ovh.com)
<LI>Go to the Public Storage console ('Public Cloud'->'Servers'->'Summit'->'Storage')
<LI>Create a public containers called Software in the BHS region
<LI>Take note of the container URL
<LI>Upload the documentation and binary into the new container
</UL>

The BHS region consists of two data centers in Beauharnois, Canada (outside of Montreal).

The container URL will be of the form https://storage.bhs1.cloud.ovh.net/v1/AUTH_LONG_STRING/Software.
Append the filename to the end of the public URL to get the download link. Test to validate that the file can be downloaded.

<UL>
<LI>Open a new browser window and enter in the download link
<LI>Verify that the file is served up from Swift and into your browser
</UL>

Congrats! You've successfully managed your first piece of content in Swift.

Now we're going to use the API to test out some more advanced features. You'll need to download the credentials from your project in order to use the API. This file contains the API URL endpoints and project info. If you aren't familiar with command line Linux, you can team up with someone that is familiar.

<UL>
<LI>Project->Compute->Access & Security->Download OpenStack RC File
<LI>Save the downloaded file to your local computer
</UL>

Using a provided Linux account, setup your OpenStack credentials.

<UL>
<LI>Use an SSH client to log into the Linux account provided.
<LI>Copy the RC file into the Linux account (cut and paste or SFTP/SCP)
<LI>Source the RC file entering in the Horizon password ("source filename-openrc.sh")
</UL>

Using the <A target="_blank" HREF="http://docs.openstack.org/developer/python-openstackclient/">OpenStackClient</A>, you're going to work with the object store. In particular, you're going to use the <A target="_blank" HREF="http://docs.openstack.org/developer/python-openstackclient/command-objects/object.html">Object commands</A> and the <A target="_blank" HREF="http://docs.openstack.org/developer/python-openstackclient/command-objects/container.html">Container commands</A>.

First we'll play with containers listing the available ones and creating a new one.
<UL>
<LI>openstack container list
<LI>openstack container show public
<LI>openstack container create docs
</UL>

Create a file and upload it into the container docs. The 'dd' command creates a file with random content.
<UL>
<LI>dd if=/dev/urandom of=docs count=1024
<LI>openstack object create public docs
<LI>openstack object show public docs
</UL>

Here are additional things to try:

<UL>
<LI>Create an HTML file and server it off Swift
<LI>Include a IMG SRC an HTML file that references the image from Swift
<LI>Create a large file and upload it as multiple segments concurrently via Swift
</UL>



