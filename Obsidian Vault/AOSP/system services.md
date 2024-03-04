In Android, [[build aosp]]system services are background processes that run on the device to perform various tasks and provide functionality to applications. These services typically handle tasks such as managing network connections, handling sensor data, managing notifications, 
### check service 
`adb shell service check com.example.gluttton.dummyandroid/.DummyService

### chech service app  in dumpsys 
 `adb shell dumpsys activity services AIDLService
 
### start service 
`adb shell am startservice com.example.gluttton.dummyandroid/.DummyService

### stop service 
`adb shell am stopservice com.example.gluttton.dummyandroid/.DummyService
