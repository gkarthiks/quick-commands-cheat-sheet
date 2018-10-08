## Install nodeJS and npm on Windows with non-admin access

**Step 1:** Download the nodeJS.exe file from the [https://nodejs.org/en/download/](https://nodejs.org/en/download/)
**Step 1:** Choose a folder to install nodeJS. For example, C:\ProgramData\Applications\nodejs

Step 2: Set 
, let's name it <NODE_PATH>.
Download the LTS node.exe binary for Windows and copy it to <NODE_PATH>.
Add <NODE_PATH> to your PATH environment variable (set PATH=<NODE_PATH>;%PATH% or using Windows user interface)
Download the stable at https://registry.npmjs.org/npm/-/npm-{VERSION}.tgz npm package (following the documentation)
Unzip the npm-{VERSION}.tgz anywhere (using 7zip for example)
Launch a cmd and cd into the place where you have unzipped npm
Execute: node cli.js install -gf or node bin/npm-cli.js install npm -gf on certain versions (thanks to this comment)
The last command is specified in the Makefile for target install, target which the README.md invites to execute when manually installing.
node bin/npm-cli.js install npm -gf
