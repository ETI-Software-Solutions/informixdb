# Installing informixdb

## Contents

1. [Overview](#Installation)
2. [Informixdb Installation on Linux](#inslnx)
3. [Informixdb Installation on AIX on Power Systems](#insaix_p)
4. [Informixdb Installation on MacOS](#insmac)
5. [Informixdb Installation on Windows](#inswin)
6. [Informixdb How to Manually Build on Windows](#inswinbld)

## <a name="overview"></a> 1. Overview

The [*Informixdb*](https://github.com/ETI-Software-Solutions/informixdb) is an asynchronous/synchronous interface for node.js to Informix Databases.

Following are the steps to create a Node.js installation for testing.


## <a name="inslnx"></a> 2. Informixdb Installation on Linux.

### 2.1 Install Node.js

Download the
[Node.js Linux binaries](http://nodejs.org) or [Node.js Latest binaries](https://nodejs.org/dist/latest/) and
extract the file, for example into `/mynode`:

```
cd /mynode
tar -xzf node-v4.2.2-linux-x64.tar.gz
```

Set PATH to include Node.js:

```
export PATH=/mynode/node-v4.2.2-linux-x64/bin:$PATH
```

### 2.2 Install informixdb

Following are the steps to install [*Informixdb*](https://github.com/ETI-Software-Solutions/informixdb) from npm and GitHub.
using directory `/nodeapp` for example.

#### 2.2.1 Direct Installation.

```
1. mkdir nodeapp
2. cd nodeapp
```

```
3. npm install @etisoftware/informixdb
```

4. Install moment (dev dependency)
```
npm install moment
```

5. Update config.testConnectionStrings.json with your credentials and run test.
```
cd node_modules/@etisoftware/informixdb/test/
vi config.testConnectionStrings.json => Update connection string in this file.
node run-tests.js
```

It's Done.

#### 2.2.2 Manual Installation by using git clone.

```
1. mkdir nodeapp
2. cd nodeapp
3. git clone https://github.com/ETI-Software-Solutions/informixdb/
```

```
4. Set "CSDK_HOME" with 'INFORMIX CSDK Installation' path, for example CSDK installation directory path is : /home/mysystem/InformixClient-SDK

export CSDK_HOME=/home/mysystem/InformixClient-SDK
```

```
5. Install node-gyp and other dependencies (refer package.json)

npm install -g node-gyp
npm install moment async bluebird
npm install nan bindings fstream q request targz unzipper
etc...
```

```
6. Set "@etisoftware/informixdb/node_modules/" path into system PATH.

export PATH=/home/mysystem/nodeapp/@etisoftware/informixdb/node_modules/.bin:$PATH
```

```
7. Run node-gyp configure build command.

node-gyp configure build --CSDK_HOME=$CSDK_HOME --verbose
```

```
8. Update config.testConnectionStrings.json with your credentials and run test.

cd @etisoftware/informixdb/test/
vi config.testConnectionStrings.json  => Update database connection info.
node run-tests.js
```

It's Done.


## <a name="insaix_p"></a> 3. Informixdb Installation on AIX on Power Systems.

### 3.1 Install Node.js for AIX

Download the
[Node.js AIX binaries](https://developer.ibm.com/node/sdk/#overview) from IBM SDK for Node.js and
execute the binary file, for example into `/mynode`:

```
cd /mynode
./ibm-4.4.3.0-node-v4.4.3-aix-ppc64.bin
```

### 3.2 Install informixdb

Follow the same steps mentioned in [Node-informixdb Installation on Linux](#inslnx).


## <a name="insmac"></a> 4. Informixdb Installation on MacOS.

### 4.1 Install Node.js for Mac

Download the
[Node.js MacOS binaries](http://nodejs.org) or [Node.js Latest binaries](https://nodejs.org/dist/latest/) and
extract the file.

### 4.2 Install informixdb

Follow the same steps mentioned in [Node-informixdb Installation on Linux](#inslnx).


## <a name="inswin"></a> 5. Informixdb Installation on Windows.

### 5.1 Install Node.js for Windows

Download the
[Node.js Windows binary/installer](http://nodejs.org) or [Node.js Latest binaries](https://nodejs.org/dist/latest/) and
install it.

### 5.2 Install informixdb

Following are the steps to install [*Informixdb*](https://github.com/OpenInformix/node-informixdb/) from npm and GitHub.
using directory `/nodeapp` for example.

```
1. mkdir nodeapp
2. cd nodeapp
```

```
3. npm install @etisoftware/informixdb
```

4. Install Install moment (dev dependency)
```
npm install moment
```

5. Update config.testConnectionStrings.json with your credentials and run test.
```
cd node_modules/@etisoftware/informixdb/test/
vi config.testConnectionStrings.json => Update connection string in this file.
node run-tests.js
```

It's Done.


## <a name="inswinbld"></a> 6. Informixdb How to Manually Build on Windows.

### 6.1 Install Node.js for Windows

Download the
[Node.js Windows binary/installer](http://nodejs.org) or [Node.js Latest binaries](https://nodejs.org/dist/latest/) and
install it.

### 6.2 Make Build informixdb

Following are the steps to build [*Informixdb*](https://github.com/ETI-Software-Solutions/informixdb/).
using directory `/nodeapp` for example.

```
1. mkdir nodeapp
2. cd nodeapp
3. git clone https://github.com/ETI-Software-Solutions/informixdb/
```

```
4. Set "CSDK_HOME" with 'INFORMIX CSDK Installation' path, for example CSDK installation directory path is : /home/mysystem/InformixClient-SDK
   and then set `CSDK_HOME` to `PATH` variable.
```

```
5. Set the msbuild path into `PATH` environment variable.
   ie.: `C:\Program Files (x86)\MSBuild\14.0\bin\`.
```

```
6. cd @etisoftware/informixdb
7. Run **npm install** command.

```

```
8. Check for `@etisoftware/informixdb\build\Release\odbc_bindings.node` file, If it's there build is successful. Well Done :cheers:
```

```
9. Update config.testConnectionStrings.json with your credentials and run test.

cd @etisoftware/informixdb/test/
vi config.testConnectionStrings.json  => Update database connection info.
node run-tests.js
```
