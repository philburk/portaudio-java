# JPortAudio - audio I/O for Java

JPortAudio is a Java wrapper for the [PortAudio](https://github.com/PortAudio/portaudio) audio library.
It provides blocking read/write streams.
JPortAudio can provide high resolution, eg. FLOAT data
and multi-channel streams that JavaSound does not support.

## Building and testing JPortAudio

### Cleaning out Old JPortAudio on MacOS

You may have an old installation of JPortAudio. You can remove it.

    rm $HOME/Library/Java/Extensions/jportaudio.jar
    rm $HOME/Library/Java/Extensions/libjportaudio.jnilib

### Build PortAudio

You can download PortAudio from [GitHub](https://github.com/PortAudio/portaudio)
or from the [website](http://files.portaudio.com/download.html).

    cd portaudio
    ./configure
    make clean
    make install

### Build JPortAudio native library

On MacOS, you may need to tell CMAKE where to look for stdio.h.

    export SDKROOT=$(xcrun --sdk macosx --show-sdk-path)
    
This should work on Linux and Mac.

    cd portaudio-java
    export LIBRARY_PATH=$LIBRARY_PATH:/usr/local/lib
    cmake .
    make install
    ls -l /usr/local/lib/lib*portaudio*

You might need to use "sudo make install".

### Build JPortAudio JAR file

    ./gradlew clean assemble
    ls -al build/libs # see JAR file

To use JPortAudio with your projects or IDE, include the JAR file in your classpath.

### Test JPortAudio JAR file

Be ready to turn down your speakers. It will play some sine tones that may be loud.

    ./gradlew clean test
