---
layout: post
title: "How to setup MATLAB functions in C++"
subtitle: "A step-by-step guide to setting up Armadillo C++ on Mac"
# date: 2020-01-26 23:45:13 -0400
# The big banner behind the blog post title
background: '/img/posts/01.jpg'
---

This is a simple and in-depth step-by-step guide to setting up Armadillo C++ on your Mac using Xcode IDE, command line tools, and installation via MacPorts. I will be starting from the <b> very beginning </b> assuming you were handed a factory-reset laptop with nothing installed on it. This guide will go through all the nitty-gritty details. Let's begin!

# Download & Install Xcode

<ul>
<li>Open up your App Store and search for "xcode"</li>
<li>Click on "GET"/"INSTALL" to start your download</li>
</ul>

<!-- ![XCode Download](/img/posts/setup-armadillo/1step.png) -->
<img src="/img/posts/setup-armadillo/1step.png" alt="XCode App Store" width="100%" height="auto"/>

## Downloading Xcode for older Macs
If you have an older Mac you can still download the version of Xcode that is compatible with it at <a href="https://xcodereleases.com"> https://xcodereleases.com </a>. 

For instance, the machine I'm downloading this software on is a 2013 Macbook Pro running on MacOS Catalina 10.15. This Mac is not compatible with the latest version of Xcode that's offered in the App Store, so I had to download the 12.4 Release version instead.

<!-- ![Older XCode Download](/img/posts/setup-armadillo/older-xcode.png) -->
<img src="/img/posts/setup-armadillo/older-xcode.png" alt="Older XCode Download" width="100%" height="auto"/>

## Installing Xcode

Once its finished downloading, double-click on the package to start the installation process. You may see some loading windows show up like the ones below.

<!-- ![XCode-install-1](/img/posts/setup-armadillo/install-xcode1.png)
![XCode-install-2](/img/posts/setup-armadillo/install-xcode2.png) -->
<img src="/img/posts/setup-armadillo/install-xcode1.png" alt="Xcode Install 1" width="100%" height="auto"/>
<img src="/img/posts/setup-armadillo/install-xcode2.png" alt="Xcode Install 2" width="100%" height="auto"/>

<h3 style="color:red;">WARNING:</h3>
If you see your Xcode program installed somewhere <em>besides</em> your "Applications" folder, you will have to drag and drop it in "Applications" before moving on.

<!-- ![Move-XCode](/img/posts/setup-armadillo/move-xcode-to-applications.png) -->
<img src="/img/posts/setup-armadillo/move-xcode-to-applications.png" alt="Move Xcode" width="100%" height="auto"/>

## Download Command-Line Developer Tools

Open Terminal. You can do this by opening Launchpad and search for "Terminal" or press ``` Cmd + [Space-Bar] ``` and search for "Terminal" in the Spotlight Search.

Once your terminal is open, type in: ``` xcode-select --install ``` and press ``` return ``` on your keyboard. You may have to put in your password that you use to sign in to your computer.

<!-- ![Terminal Install Cmd Line Tools](/img/posts/setup-armadillo/cmd-line-tools-install.png) -->
<img src="/img/posts/setup-armadillo/cmd-line-tools-install.png" alt="Terminal Install Command-line Tools" width="100%" height="auto"/>


A window should pop up asking if you want to install the command-line developer tools. Click on the "Install" button.

<!-- ![cmd line install prompt](/img/posts/setup-armadillo/install-prompt-cmd-line.png) -->
<img src="/img/posts/setup-armadillo/install-prompt-cmd-line.png" alt="Command-Line Install Prompt" width="100%" height="auto"/>

Once it has finished, you will now have to agree to Apple/Xcode Terms & Conditions. Go back to your terminal window and type in : ``` sudo xcodebuild -license ``` and hit ``` return ``` on your keyboard. You may be prompted for your password again. 

<!-- ![xcode license](/img/posts/setup-armadillo/xcode-license.png)
![Terms and Conditions Xcode](/img/posts/setup-armadillo/terms-conditions.png) -->

<img src="/img/posts/setup-armadillo/xcode-license.png" alt="xcode license" width="100%" height="auto"/>
<img src="/img/posts/setup-armadillo/terms-conditions.png" alt="Terms and Conditions Xcode" width="100%" height="auto"/>


The Terms and Conditions should show up on the Terminal, read and scroll through the entire documenation and type in ```agree``` in the terminal if you choose to agree to the terms. 

# Install MacPorts

You will now have to install MacPorts. Go to <a href="https://www.macports.org/install.php"> https://www.macports.org/install.php </a>. Under "Quickstart" click on one of the bulleted links based on your system.

<!-- ![MacPorts Link](/img/posts/setup-armadillo/macports-link.png) -->
<img src="/img/posts/setup-armadillo/macports-link.png" alt="" width="100%" height="auto"/>

Once you download MacPorts, open the MacPorts package. Most likely it is in your downloads folder. You will then go through the steps for installation. Go through the necessary prompts.

<center>
<img src="/img/posts/setup-armadillo/macports-pkg.png" alt="MacPorts Pkg" width="50%" height="400"/>
</center>

<img src="/img/posts/setup-armadillo/macports-install.png" alt="MacPorts Install" width="100%" height="auto"/>

# Download & Install Armadillo C++ Library

Now that we *finally* have all those prerequsites out of the way, we will now download our Armadillo C++ libary. 

* Go to <a href="http://arma.sourceforge.net/download.html">http://arma.sourceforge.net/download.html</a>
* Scroll down to "Installation Notes", under the **macOS** bullet-point you will see a link to install via <a href="https://ports.macports.org/search/?q=armadillo">MacPorts</a>

<img src="/img/posts/setup-armadillo/armadillo-install-page.png" alt="" width="100%" height="auto"/>

* Click on the <a href="https://ports.macports.org/port/armadillo/">armadillo</a> link and the following page should appear:

<img src="/img/posts/setup-armadillo/macports-armadillo-cmd.png" alt="" width="100%" height="auto"/>

* Copy & Paste the command line to your terminal to download Armadillo library. The command-line at the time of this writing is ```sudo port install armadillo```

<img src="/img/posts/setup-armadillo/armadillo-terminal-cmd-install.png" alt="" width="100%" height="auto"/>

* Hit ```return``` and go through the necessary prompts to finish installation

The armadillo files should have been downloaded in your ```/opt/locol``` folder. To double-check, type in your terminal ```cd /opt/local/lib``` and press ```return```. Then type in ```ls``` and hit ```return``` again. You should see file names like ```libarmadillo.dylib``` and ```libhdf5.dylib``` show up as below:

<center>
<img src="/img/posts/setup-armadillo/terminal-arma-files-list.png" alt="" width="80%" height="auto"/>
</center>


# Setup Armadillo with Xcode

Open up Xcode. On the welcome screen, select "Create a new Xcode project"

<center>
<img src="/img/posts/setup-armadillo/xcode-welcome.png" alt="" width="80%" height="auto"/>
</center>

A window will pop up saying "Choose a template for your new project:". Select the "macOS" option that is towards the top of that window and then select the "Command Line Tool" in the Application section. Click the "Next" button.

<img src="/img/posts/setup-armadillo/xcode-cmd-line-tool.png" alt="" width="100%" height="auto"/>

Fill out the "Product Name:" and "Organization Identfier" (this can be anything you want).
In the "Language" dropdown select ```C++```.

<img src="/img/posts/setup-armadillo/create-cpp-project.png" alt="" width="100%" height="auto"/>

Select a location where you want your project files to live within your computer and click "Create".

You will be presented with the following Xcode project layout:

<img src="/img/posts/setup-armadillo/xcode-init-layout.png" alt="" width="100%" height="auto"/>

### Adding Header Search Paths

We will be adding the Armadillo search path to our project.

1. Click on your project name on the left-side panel. 
2. Click on the "Build Settings" tab 
3. In the search bar type: "Header Search Paths"
4. Double-click the whitespace next to "Header Search Paths" listed in the main window. An empty whitebox should appear below
5. Click on the ```+``` symbol on the bottom left of that window
6. Add: ```/opt/local/include``` and hit ```return```

<img src="/img/posts/setup-armadillo/header-search-paths.png" alt="" width="100%" height="auto"/>

This is how it should look when you're finished:

<img src="/img/posts/setup-armadillo/header-search-path-done.png" alt="" width="100%" height="auto"/>

### Adding the Library Search Path

Staying in the "Build Settings" tab search for "Library Search Paths" and add ```/opt/local/lib``` similar to how the Header Search Path was added. This is how it should look once you're done:

<img src="/img/posts/setup-armadillo/library-search-paths.png" alt="" width="100%" height="auto"/>

### Adding Linker Flags

Still within the "Build Settings" tab search for "Other Linker Flags" and add ```-larmadillo``` similar to how the Header Search Path and Library Search Path was added. This is how it should look once you're done:

<img src="/img/posts/setup-armadillo/linker-flag.png" alt="" width="100%" height="auto"/>

# Using Armadillo functions in your code!

We should be set to use Armadillo functions now! On the left-side panel under your project's name folder, there should be some C++ starter code called ```main.cpp```. Click on it to open it.

<img src="/img/posts/setup-armadillo/starting-main.png" alt="" width="100%" height="auto"/>

Add the headers towards the top of your code:
```cpp
 #include "armadillo"
 using namespace arma;
```
And test out many of the convenient functions that Armadillo C++ has to offer. You can get familiar with these functions through their documentation page: <a href="http://arma.sourceforge.net/docs.html">http://arma.sourceforge.net/docs.html</a>

Try some out and Build + Run your code by clicking the big Play Button at the top of the Xcode window. You can see me create and print a 3 x 3 matrix of zeros below. 

<img src="/img/posts/setup-armadillo/armadillo-test.png" alt="" width="100%" height="auto"/>

# Some Issues... Or should I say "Warnings"?

If you're like me, when I first Built + Ran my code, it ran successfully but with over 100 warnings popping up, which can be annoying to say the least. This is what it looked like for me:

<img src="/img/posts/setup-armadillo/armadillo-warnings.png" alt="" width="100%" height="auto"/>


<!-- <img src="/img/posts/setup-armadillo/.png" alt="" width="" height="auto"/> -->