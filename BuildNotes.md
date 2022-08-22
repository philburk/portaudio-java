# Build Note for JPortAudio

3/19/21 - When I run ChebyshevSong with the old jportaudio-0.1.0.jar
then AudioDeviceFactory cannot load "com.portaudio.PortAudio"

I added LD_LIBRARY_PATH = /usr/local/lib to the Eclipse Run Configuration Environment Tab.

Or, as an alternative:
    cp /usr/local/lib/libjportaudio_0_1_0.dylib $HOME/Library/Java/Extensions/.

Then I got: ---- JPortAudio 0.1.0, PortAudio V19.7.0-devel, revision unknown
when I ran ChebyshevSong.  Note 19.7.0 version!!!
