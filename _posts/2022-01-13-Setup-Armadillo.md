---
layout: post
title: "How to setup MATLAB functions in C++"
subtitle: "A step-by-step guide to setting up Armadillo C++ on Mac"
# date: 2020-01-26 23:45:13 -0400
# The big banner behind the blog post title
background: '/img/posts/01.jpg'
---

This is a simple step-by-step guide to setting up Armadillo C++ on your Mac. I will be starting from the <b> very beginning </b> assuming you were handed a brand new laptop with nothing installed on it. This guide will go through all the nitty-gritty details. Let's begin!

# Download & Install Xcode

<ul>
<li>Open up your App Store and search for "xcode"</li>
<li>Click on "GET"/"INSTALL" to start your download</li>
</ul>

![XCode Download](/img/posts/setup-armadillo/1step.png)

## Downloading Xcode for older Macs
If you have an older Mac you can still download the version of Xcode that is compatible with it at <a href="https://xcodereleases.com"> https://xcodereleases.com </a>. 

For instance, the machine I'm downloading this software on is a 2013 Macbook Pro running on MacOS Catalina 10.15. This Mac is not compatible with the latest version of Xcode that's offered in the App Store, so I had to download the 12.4 Release version instead.

![Older XCode Download](/img/posts/setup-armadillo/older-xcode.png)

## Installing Xcode

Once its finished downloading, double-click on the package to start the installation process. You may see some loading windows show up like the ones below.

![XCode-install-1](/img/posts/setup-armadillo/install-xcode1.png)
![XCode-install-2](/img/posts/setup-armadillo/install-xcode2.png)

<h3 style="color:red;">WARNING:</h3>
If you see your Xcode program installed somewhere <em>besides</em> your "Applications" directory, you will have to drag and drop it in "Applications" before moving forward.

![Move-XCode](/img/posts/setup-armadillo/move-xcode-to-applications.png)

## Download Command-Line Developer Tools

Open Terminal. You can do this by opening Launchpad and search for "Terminal" or press ``` Cmd + [Space-Bar] ``` and search for "Terminal" in the Spotlight Search.

Once your terminal is open, type in: ``` xcode-select --install ``` and press ``` return ``` on your keyboard. You may have to put in your password that you use to sign in to your computer.

![Terminal Install Cmd Line Tools](/img/posts/setup-armadillo/cmd-line-tools-install.png)


A window should pop up asking if you want to install the command-line developer tools. Click on the "Install" button.

![cmd line install prompt](/img/posts/setup-armadillo/install-prompt-cmd-line.png)

Once it has finished, you will now have to agree to Apple/Xcode Licence. Go back to your terminal window and type in : ``` sudo xcodebuild -license ``` and hit ``` return ``` on your keyboard. You may be prompted to type in you password to sign in to your computer again. 

![xcode license](/img/posts/setup-armadillo/xcode-license.png)
![Terms and Conditions Xcode](/img/posts/setup-armadillo/terms-conditions.png)


The Terms and Conditions should show up on the Terminal, read and scroll through the entire documenation and type in ```agree``` in the terminal if you choose to agree to the terms. 

<!-- ![](/img/posts/setup-armadillo/.png) -->
