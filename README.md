# Pamux Studios, C++ Project Template

## Install on the machine where you'll run the VS Code IDE:

* Install [VS Code](https://code.visualstudio.com/download)

* Install [C++ Extension for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)

* Install [CMake Tools Extension for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools)

* Install [Remote Development Extensions for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)

## Install on the machine where you'll build the code for (Ubuntu 24.04 LTS @ WSL in my case):

    sudo apt-get update

[Git WSL Tutorial](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-git)

Install Git:
    sudo apt-get install git

Or Upgrade Git:

    sudo add-apt-repository ppa:git-core/ppa -y
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install git -y

Make sure you installed the latest:

    git --version

Configure global git:

    git config --global user.name "yazici"
    git config --global user.email "yazici.b@gmail.com"

For git > 2.39:

    git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/bin/git-credential-manager.exe"

View your global config:

    vi ~/.gitconfig

Install other build, etc. tools:

    sudo apt-get install curl zip unzip tar
    sudo apt-get install pkg-config
    sudo apt-get install build-essential gdb
    sudo apt-get install ninja-build
    sudo apt-get install ca-certificates gpg wget

Install latest CMake (2.29.2 is required min version)
[Latest CMake](https://apt.kitware.com/)

    # To create $DISTRIB_CODENAME env variable
    source /etc/lsb-release

    KEYRING_PATH=/usr/share/keyrings/kitware-archive-keyring.gpg

    test -f /usr/share/doc/kitware-archive-keyring/copyright || wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null | gpg --dearmor - | sudo tee $KEYRING_PATH >/dev/null


    echo 'deb [signed-by=$KEYRING_PATH] https://apt.kitware.com/ubuntu/ $DISTRIB_CODENAME main' | sudo tee /etc/apt/sources.list.d/kitware.list >/dev/null

    sudo apt-get update

## git

[Git Credential Manager](https://github.com/git-ecosystem/git-credential-manager/blob/main/README.md)

[Git-Tools-Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)

## Clang Format

## vcpkg
[VCPKG Overview](https://learn.microsoft.com/en-us/vcpkg/get_started/overview)


Adding an existing project as submodule, so it is pulled and built automatically:

    cd ~/src/Pamux.CPP
    git submodule add https://github.com/microsoft/vcpkg

## CMAKE

[vscode-cmake-tools](https://github.com/microsoft/vscode-cmake-tools/blob/main/docs/README.md)

    cmake --version

## GCC

[GCC on WSL](https://code.visualstudio.com/docs/cpp/config-wsl)

    gcc -v
    whereis g++
    whereis gdb

## VS Code

[C++ for Visual Studio Code](https://code.visualstudio.com/docs/languages/cpp)

[VSCode Markdown](https://code.visualstudio.com/docs/languages/markdown) - This ile is a *markdown*

## Ninja Build System

[Ninja Build System](https://ninja-build.org/)


[Pre-built-Ninja-packages](https://github.com/ninja-build/ninja/wiki/Pre-built-Ninja-packages)


# apt


## VS Code Command Palette (CTRL-SHIFT-P)

* CMake: Configure

    [proc] Executing command: /usr/bin/cmake -DCMAKE_INSTALL_PREFIX=/home/baris/src/Pamux.CPP/out/install/ninja-multi-vcpkg -DCMAKE_C_COMPILER=/usr/bin/gcc -DCMAKE_CXX_COMPILER=/usr/bin/g++ -DCMAKE_BUILD_TYPE=Debug -DCMAKE_TOOLCHAIN_FILE=/home/baris/src/Pamux.CPP/vcpkg/scripts/buildsystems/vcpkg.cmake -S/home/baris/src/Pamux.CPP -B/home/baris/src/Pamux.CPP/builds/ninja-multi-vcpkg -G "Ninja Multi-Config"

* CMake: Build

    [proc] Executing command: /usr/bin/cmake --build /home/baris/src/Pamux.CPP/builds/ninja-multi-vcpkg --config Debug --

* CMake: Debug

    [proc] Executing command: /usr/bin/cmake --build /home/baris/src/Pamux.CPP/builds/ninja-multi-vcpkg --config Debug --target PamuxCPP --

* CMake: Run without Debugging

    /home/baris/src/Pamux.CPP/builds/ninja-multi-vcpkg/Debug/PamuxCPP  (executable)