Air Native Extension for testing network connection (iOS + Android)
======================================

This is an [Air native extension](http://www.adobe.com/devnet/air/native-extensions-for-air.html) to if the current device has an active connection. It has been developed by [FreshPlanet](http://freshplanet.com) and is used in the game [SongPop](http://songpop.fm).


Installation
---------

The ANE binary (AirNetworkInfo.ane) is located in the *bin* folder. You should add it to your application project's Build Path and make sure to package it with your app (more information [here](http://help.adobe.com/en_US/air/build/WS597e5dadb9cc1e0253f7d2fc1311b491071-8000.html)).


On Android:

* you need to enable the following permissions (otherwise the returned state will always be not connected):

    ```xml
    <android>
        <manifestAdditions><![CDATA[
            <manifest android:installLocation="auto">
                
                ...

                <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
                <uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
                
                ...

            </manifest>
        ]]></manifestAdditions>
    </android>
    ```


Usage
---------

Call the function *AirNetworkInfo.networkInfo.isConnected()* to check the current network status of the device.


Build script
---------

Should you need to edit the extension source code and/or recompile it, you will find an ant build script (build.xml) in the *build* folder:

    cd /path/to/the/ane/build
    mv example.build.config build.config
    #edit the build.config file to provide your machine-specific paths
    ant


Authors
------

This ANE has been written by [Thibaut Crenn](https://github.com/titi-us). It belongs to [FreshPlanet Inc.](http://freshplanet.com) and is distributed under the [Apache Licence, version 2.0](http://www.apache.org/licenses/LICENSE-2.0).
