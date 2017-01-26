# swift-tutorial
Using OpenStack Swift Object Store

You've been tasked with making your companies software and documentation available via the Internet. You've decided to put the files onto a OpenStack Swift Object powered cloud. Swift provide a reliable image store with API access to upload, download and manage the content.

<UL>
<LI>Download the file: http://ossd.openstacksandiego.org:8080/v1/AUTH_5ff6951f221d401b9fca8b2f8816440c/public/beerkeg.jpg
<LI>Download the file: http://ossd.openstacksandiego.org:8080/v1/AUTH_5ff6951f221d401b9fca8b2f8816440c/public/cookie.jpg
<LI>Assign yourself an account from the <A HREF="https://etherpad.openstack.org/p/san-diego-swift">Etherpad</A> https://etherpad.openstack.org/p/san-diego-swift The password to the account is on the whiteboard.
</UL>

Swift stores files into containers. First step is to create a new container and upload the documentation into the new container. 
<UL>
<LI>Log into <A HREF="https://ossd.openstacksandiego.org">OpenStack San Diego Cloud</A> (https://ossd.openstacksandiego.org/
<LI>Go to the storage link ('Object Store' -> 'Containers')
<LI>Create a public containers called Public
<LI>Take note of the container URL
<LI>Upload the images into the new container
</UL>

The container URL will be of the form https://ossd.openstacksasndiego.org:8080/v1/AUTH_LONG_STRING/Public.
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

Here are additional things to try:

<UL>
<LI>Create an HTML file and server it off Swift
<LI>Include a IMG SRC an HTML file that references the image from Swift
<LI>Create a large file and upload it as multiple segments concurrently via Swift
</UL>



