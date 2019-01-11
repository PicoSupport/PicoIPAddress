<p align="right"><a href="https://github.com/PicoSupport/PicoSupport" target="_blank"> <img src="https://github.com/PicoSupport/PicoSupport/blob/master/Assets/home.png" width="20"/> </a></p>

# IPAddressManager Instructions

Note: Regarding java package creation and usege, please refer to [the Guideline](https://github.com/PicoSupport/PicoSupport/blob/master/Call%20And%20Export%20Jar.docx)

1. Create a new Unity project and copy the PicovrWifiManager_vxxx. Jar package in the plugins-> Android in the Demo to the directory corresponding to the Unity project.

2. Modify AndroidMinifest.xml .Add Permission

   ```
   <uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
   <uses-permission android:name="android.permission.CHANGE_WIFI_STATE"/>
   <uses-permission android:name="android.permission.WRITE_SETTINGS"/>
   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
   <uses-permission android:name="android.permission.INTERNET" />
   <uses-permission android:name="android.permission.WAKE_LOCK" />
   
   ```

   Modify MainActivity :

   ```
   android:name=" com.example.picovripaddress.picovrWifiManager"
   ```
   ![](https://github.com/PicoSupport/PicoIPAddress/blob/master/01.png)

3. Copy the script of PicoUnityActivity. cs in the Demo to any directory of Unity project.

4. Call Android interface : For example Call Android's Wifi interface

   ```
   PicoUnityActivity.CallObjectMethod("adnroidConnectWifi", new object[] { "pico_tob", "pico2016" });
   ```

   ​                                                                  Interface Instructions

   | Interface           | Explain                 | Remark                                                       |
   | ------------------- | ----------------------- | :----------------------------------------------------------- |
   | adnroidConnectWifi  | Wifi Connection         | PicoUnityActivity.CallObjectMethod("adnroidConnectWifi",<br/>new object[] { "username", "password" }); |
   | androidGetIpAddress | Get IP address          | string ip="" ;            PicoUnityActivity.CallObjectMethod<string>(ref<br/>ip, "androidGetIpAddress"); |
   | androidGetGateWay   | Get the gateway address | string gateway="";  PicoUnityActivity.CallObjectMethod<string>(ref<br/>gateway, "androidGetGateWay"); |
   | androidGetDNS       | Get DNS                 | string mdns="";        PicoUnityActivity.CallObjectMethod<string>(ref<br/>mdns, "androidGetDNS"); |
   | androidSetIpAddress | Set Ip address          | PicoUnityActivity.CallObjectMethod("androidSetIpAddress", new object[] { "username", "password","ip address","gateway","DNS" }); |

