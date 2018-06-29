-----------------------------------------------
## Getting Started  

To start developing a Symptomatic Plugin, you're going to need to set up a complete development environment.  There's a large ecosystem of tools to use, so the focus in this document is on tools that are known to work together well on **Mac OSX**.   


**App Development**  
[Meteor](https://www.meteor.com/) - Isomorphic javascript/node environment.  
[GitHub Desktop App](https://desktop.github.com/) - For synchronizing and managing code.    
[Visual Studio Code](https://code.visualstudio.com/) - Editor with support for large files (genomics, big data) and good javascript refactoring tools.  

**Platform Development**    
[Java 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) - Needed QA testing tools.  
[Node JS](http://nodejs.org/en/) - Server-side javascript environment. Use the LTS release.    
[Visual Studio - Community 2017](https://www.visualstudio.com/downloads/) - C++ compilers needed for some Node libraries.    


-----------------------------------------------
#### Chrome Environment  

Clinical Meteor prefers a Chrome environment.  So much so, that its arguably an alternative Chrome OS.  Not only will we be targeting Chrome as our preferred browser; we'll also be installing utilities as Chrome extensions; using a code editor built on Chrome, and using Chrome in our QA test runner.  Clinical Meteor supports other browsers (particularly Firefox and Safari), but the bulk of it's work is done with Chrome.  

Once you get Chrome installed, we recommend the following extensions; which will help develop Clinical Meteor apps.  

[Chrome](https://www.google.com/chrome/browser/desktop/) - Prefered web browser.  
[Postman HTTP/REST Utility](https://www.getpostman.com/) - HTTP protocol utility for programming REST interfaces.  
[MeteorDevTools](https://chrome.google.com/webstore/detail/meteor-devtools/ippapidnnboiophakmmhkdlchoccbgje) - Blaze, DDP, and Minimongo debugging utilities.


-----------------------------------------------
#### Version Control Software     

The easiest way to install `git` is to install the [GitHub Desktop App](https://desktop.github.com/).  You'll then have access to both the GUI and the command line.   

```sh
$ git config --global user.name "Jane Doe"
$ git config --global user.email janedoe@example.com
$ git config --global core.editor atom -w
```

-----------------------------------------------
#### Meteor Installation Walkthrough  

This quickstart is written for Mac OSX Mavericks, and is a bit more verbose than other installation instructions.  It should hopefully cover a few edge cases, such as setting your path, which can cause an installation to go awry.  

````sh
# install meteor
curl https://install.meteor.com | sh

# check it's installed correctly
meteor --version

# install npm
curl -0 -L https://npmjs.org/install.sh | sh

# check node is installed correctly
node --version

# check npm is installed correctly
npm -version

# find your npm path
which npm

# make sure npm is in your path
sudo nano ~/.profile
  export PATH=$PATH:/usr/local/bin
 ````


If you have any problems with EACCESS pr ENOENT errors, check the file permissions of your NPM directories.  
https://docs.npmjs.com/getting-started/fixing-npm-permissions


-----------------------------------------------
#### Database Tools  

[Robomongo](http://robomongo.org/) - A sweet, sweet database management tool for MongoDB.

Here's the script the author uses when setting up a new development workstation.  It's certainly not the only environment setup script, and it's by no means authoritative.  It's simply what seems to work.


-----------------------------------------------
#### Project Management Tools  

[Slack](https://slack.com/) - Collaborative project tracking feeds.    
[InVision Sync](http://blog.invisionapp.com/an-all-new-invision-sync/) - Collaborative wireframing and prototyping.  
[Zenhub.io](zenhub.io) - Project management Kanban boards for GitHub.  
