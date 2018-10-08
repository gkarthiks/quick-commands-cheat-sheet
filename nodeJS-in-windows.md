## Install nodeJS and npm on Windows with non-admin access

**Step 1:** Download the nodeJS.exe file from the [https://nodejs.org/en/download/](https://nodejs.org/en/download/) by clicking on `All download options` and choose the right windows arch and download it.

**Step 2:** Choose a folder to for nodeJS. For example, `C:\ProgramData\Applications\nodejs` and save the downloaded file under this folder.

**Step 3:** Add the nodeJS folder to the environment variable `PATH` by executing the below command in the `cmd.exe`.

> set PATH=C:\ProgramData\Applications\nodejs;%PATH% 

**Step 4:** Now download the stable version of `npm` from the below link by replacing the version.
[https://registry.npmjs.org/npm/-/npm-{VERSION}.tgz](https://registry.npmjs.org/npm/-/npm-{VERSION}.tgz)

For example for npm version 6.4.1, https://registry.npmjs.org/npm/-/npm-6.4.1.tgz

**Step 5:** Now unzip the downloaded npm file anywhere and `cd` into `package` folder.

**Step 6**: Execute the following command in the `cmd.exe`

> node bin/npm-cli.js install npm -gf

**Step 7**: Execute the following commands to verify the installation of nodeJS and npm.

> node -v

> npm -v
