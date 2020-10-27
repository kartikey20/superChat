
superChat is a photo and file sharing application built on Android and is inspired by Snapchat. The project's
goals are to develop a completely decentralized application that runs over the Named Data Network (NDN), utilize
a partial sync protocol, and utilize a Web-Of-Trust like model instead of the traditional NDN hierarchical model.

## Prerequisites
superChat requires the NDN Forwarding Daemon be run alongside it. NFD can be installed via [Google Play](https://play.google.com/store/apps/details?id=net.named_data.nfd) or directly from the [source](https://github.com/named-data-mobile/NFD-android).

## Building

### Getting PSync JNI

This build depends on PSync JNI. Clone [Android Crew Staging](https://github.com/named-data-mobile/android-crew-staging) in
your `Android/Sdk/ndk-bundle` folder and install ndn-cxx and prerequisites.
NFD is not needed unless you plan to build [NFD-android](https://github.com/named-data-mobile/NFD-android).
Being in the ndk-bundle directory, execute the following commands:

    CREW_OWNER=named-data-mobile crew.dir/crew install target/sqlite target/openssl
    CREW_OWNER=named-data-mobile crew.dir/crew install target/boost target/ndn_cxx
    CREW_OWNER=named-data-mobile crew.dir/crew install target/psync

Use `--no-check-shasum` if there are problems with shasum.

Also add these `local.properties` file if not already added:

    ndk.dir=/path/to/Android/Sdk/ndk-bundle
    sdk.dir=/path/to/Android/Sdk

### Building superChat

After installing PSync, it is recommended that one uses Android Studio to build the app.
Simply pull this repository and allow the project to build itself.
No other installations are required at this point of time.
All other dependencies are pulled from external sources when the build file executes.
This application only works on Android OS 6.0 and above.
