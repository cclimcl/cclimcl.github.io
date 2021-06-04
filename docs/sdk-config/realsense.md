# Intel RealSense Configuration

This section of the d.ASH SDK documentation provides details about the configuration file for the robot `realSenseConfig.json`. Information in this section includes variable and definitions to configure [Intel RealSense](/getting-started/dash-server#intel-realsense).

```json
{
    "test" : true,
    "testFilenames" : ["../../test_videos/nus_left.mp4", "../../test_videos/nus_center.mp4","../../test_videos/nus_right.mp4"],
    "flipOptions" : {
        "0" : [false, false],
        "1" : [false, false]
    },
    "baseWidth" : 640,
    "baseHeight" : 360,
    "codec" : "video",
    "width" : 320,
    "height" : 240,
    "bitrate" : 450000
}
```

- **`test`**: This streams any attached hardware RealSense devices. Default is set to `false`. If you set `test` to `true`, then you can simulate camera streaming via provided custom **mp4 video files** specified as a list in `testFilenames`.
- **`flipOptions`**: This allows you to specific how you want to flip each camera (based on index) along the X and Y axes. The format is that of a map/table: `{ "index" : [ flipX, flipY] }`
- **`codec`**: This has **jpg** or **video** options, with **jpg** being regular jpeg encoding (larger size but more stable) and **video** using VP9 encoding. 
- **`baseWidth`**: Adjusts the processing width of the camera stream. 
- **`baseHeight`**: Adjusts the processing height of the camera stream. 
!!! note "Processed Resolution"
    The video will be actually processed at this resolution before being resized via `width` and `height`. This means you can potentially have a higher/lower resolution for the actual processed camera stream vs the returned/final size. You need this because sometimes you might want to change the actual processed resolution due to power/efficiency considerations of the RealSense devices. 
- **`width`**: Adjusts the final returned/resized width dimensions of the input camera stream
- **`height`**: Adjusts the final returned/resized height dimensions of the input camera stream
!!! note "Video Streaming"
    For video streaming, you need this to be at least a `baseWidth` of *640* and a `baseHeight` of *360* starting out. 
- **`bitrate`**:  This is the quality of the video encoding [only applies to video streaming]
!!! note "HD Streaming"
    For HD Streaming, RealSense requires a high bitrate of 3600000. This value has been tested to work well with control.
- **`odomCam`**: [**OPTIONAL**] This is a parameter that you **must set** if you want to use odom streaming for RealSense. If you have `odomStreamCam` setup in the main **`robotConfig.json`**, then you must also setup `odomCam` in `realSenseConfig.json`. This tells the setup to use a particular type of RealSense camera. For example:

```json
{
    "test" : true,
    "testFilenames" : ["../../test_videos/nus_left.mp4", "../../test_videos/nus_center.mp4","../../test_videos/nus_right.mp4"],
    "flipOptions" : {
        "0" : [false, false],
        "1" : [false, false]
    },
    "baseWidth" : 640,
    "baseHeight" : 360,
    "codec" : "video",
    "width" : 320,
    "height" : 240,
    "bitrate" : 450000
    "odomCam" : "D455"
}
```

