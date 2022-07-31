# Build Note for JPortAudio

## Mac OS

### Cleaning out Old JPortAudio

I kept linking to an old installation of JPortAudio

    rm $HOME/Library/Java/Extensions/jportaudio.jar
    rm $HOME/Library/Java/Extensions/libjportaudio.jnilib

### Build PortAudio

    ./configure
    make clean
    make install

### Build JPortAudio

    export LIBRARY_PATH=$LIBRARY_PATH:/usr/local/lib
    cmake .
    make install
    ls -l /usr/local/lib/lib*portaudio*

### Notes

3/19/21 - When I run ChebyshevSong with the old jportaudio-0.1.0.jar
then AudioDeviceFactory cannot load "com.portaudio.PortAudio"

I added LD_LIBRARY_PATH = /usr/local/lib to the Eclipse Run Configuration Environment Tab.

Or, as an alternative:
    cp /usr/local/lib/libjportaudio_0_1_0.dylib $HOME/Library/Java/Extensions/.

Then I got: ---- JPortAudio 0.1.0, PortAudio V19.7.0-devel, revision unknown
when I ran ChebyshevSong.  Note 19.7.0 version!!!

10/30/21