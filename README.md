# seL4test

This repository contains instructions for fetching, configuring, and running `seL4test` on a simulator using the seL4 microkernel.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Fetching the Sources](#fetching-the-sources)
- [Configuring the Build](#configuring-the-build)
- [Building the Project](#building-the-project)
- [Running seL4test](#running-sel4test)
- [Expected Output](#expected-output)

## Prerequisites

Make sure you have the following installed:
- **Repo**: A tool for managing multiple Git repositories.
- **CMake**: A build system generator.
- **Ninja**: A small build system with a focus on speed.
- **QEMU**: A generic and open-source machine emulator and virtualizer.

## Fetching the Sources

First, create a directory for `seL4test` and initialize the repo:

```bash
mkdir seL4test
cd seL4test
repo init -u https://github.com/seL4/sel4test-manifest.git
repo sync
```

## Configuring the build

Next, create a build directory for the x86_64 platform with simulation support

```bash
mkdir build-x86
cd build-x86
../init-build.sh -DPLATFORM=x86_64 -DSIMULATION=TRUE
```

### Building the Project

After configuring, build the project using Ninja

```bash
ninja
```
### Running Sel4test
Run the test with QEMU
```bash
./simulate
```

### Expected Output

```php
Test VSPACE0002 passed

        </testcase>

        <testcase classname="sel4test" name="Test all tests ran">

        </testcase>

</testsuite>

All is well in the universe
```

