***References:*** https://askubuntu.com/questions/355565/how-do-i-install-the-latest-version-of-cmake-from-the-command-line/865294

1. Uninstall the default version provided by Ubuntu's package manager:

    ```
    sudo apt remove cmake
    sudo apt purge --auto-remove cmake
    ```

2. Go to the official CMake webpage, then download and extract the latest version. Update the `version` and `build` variables in the following command to get the desired version:

    ```
    version=3.11
    build=1
    mkdir ~/temp
    cd ~/temp
    wget https://cmake.org/files/v$version/cmake-$version.$build.tar.gz
    tar -xzvf cmake-$version.$build.tar.gz
    cd cmake-$version.$build/
    ```

3. Install the extracted source by running:

    ```
    ./bootstrap
    make -j4
    sudo make install
    ```

4. Test your new `cmake` version.

    ```
    $ cmake --version
    ```

    Results of `cmake --version`:

    ```
    cmake version 3.11.X
    
    CMake suite maintained and supported by Kitware (kitware.com/cmake).
    ```
