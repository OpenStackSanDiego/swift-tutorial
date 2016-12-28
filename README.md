# swift-tutorial
Using OpenStack Swift Image Store

You've been tasked with making your companies software and documentation available via the Internet. You've decided to put the files onto a OpenStack Swift powered cloud. Swift provide a reliable image store with API access to upload, download and manage the content.

<UL>
<LI>Get a copy of the files to distribute
<LI>Assign yourself an account from the <A HREF="https://etherpad.openstack.org/p/san-diego-swift">Etherpad</A> https://etherpad.openstack.org/p/san-diego-swift
</UL>


<UL>
<LI>Log into <A HREF="https://ca.ovh.com">OVH</A> (https://ca.ovh.com)
<LI>Go to the Public Storage console ('Public Cloud'->'Servers'->'Summit'->'Storage')
<LI>Create a public containers called Software in the BHS region
<LI>Take note of the container URL
<LI>Upload the documentation and binary into the new container
</UL>

The BHS region consists of two data centers in Beauharnois, Canada (outside of Montreal).

The container URL will be of the form https://storage.bhs1.cloud.ovh.net/v1/AUTH_LONG_STRING/Software.
Append the filename to the end of the public URL to get the download link.

<UL>
<LI>Open a new browser window and enter in the download link
<LI>Verify that the file is served up from Swift and into your browser
</UL>

Congrats! You've successfully managed your first piece of content in Swift.

Now we're going to use the API to test out some more advanced features. You'll need to download the credentials from your project in order to use the API. This file contains the API URL endpoints and project info.

<UL>
<LI>Project->Compute->Access & Security->Download OpenStack RC File
<LI>Save the downloaded file to your local computer
</UL>

Using the <A HREF="http://docs.openstack.org/developer/python-openstackclient/" target="_blank">OpenStackClient</A>, you're going to work with the object store. In particular, you're going to use the <A HREF="http://docs.openstack.org/developer/python-openstackclient/command-objects/object.html" target="_blank">Object Store commands</A


xxxx 

