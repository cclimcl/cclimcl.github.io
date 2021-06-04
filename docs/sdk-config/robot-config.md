# 1.0 Robot Configuration

This section of the d.ASH SDK documentation provides details about the configuration file for the robot `robotConfig.json`. Information in this section includes variable and definitions used to configure the [d.ASH server](../index.md#dash-server).

### 1.1 ^^Config File^^
``` json
{
    "serverAddress" : "localhost:50051",
    "robotHostname" : "192.168.80.3",
    "username" : "user5",
    "camList" : ["RealsenseCam"],
    "payloads" : [],
    "dataStateLogFolder" : "C:/Users/kestr/Documents/Projects/robotDataState",
    "ssl" : true,
    "fastServer" : false,
    "fastServerHostname" : "localhost:7777",
    "secureDefaultToken" : false,
    "testMode" : true,
    "withAudio" : false
}
```
<p>&nbsp;</p>

### 1.2 ^^Definitions^^

- **`serverAddress`** : Sets address of the spotServer in `<HOSTNAME>:<PORT>` format.
- **`robotHostname`** : Sets hostname of the Spot to connect to robot's IP.
- **`username`** : Sets username to log into the Spot.
- **`camList`** : Sets a list of cameras active for the current session i.e. *RealsenseCam*.
---
- **`payloads`** : Optional payloads list.
- **`dataStateLogFolder`** : Sets folder to write out the recorded msgpack data of the robot i.e. *cameras, odom etc.*
- **`ssl`** : Enables secure SSL messaging and encryption.
- **`fastServer`** : ???
- **`fastServerHostname`** : ???
---
!!! note "The following parameter should always be set to **`False`**. Use the **`<!TOKEN!>`** method in the Robot Rest Service to pass the authentication token in."

- **`secureDefaultToken`** : ???

---
- **`testMode`** : Enables the Spot server to enter into test mode.
- **`withAudio`** : Enables audio streaming playback.
