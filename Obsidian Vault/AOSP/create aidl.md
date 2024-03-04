### 1-Create AIDL Interfcae .aidl 
> ITelephonyService.aidl 
package com.example; 
interface ITelephonyService { 
void makePhoneCall(String phoneNumber); int getSignalStrength();
// ... other methods }
t 
### 2-build/generate [[Generate aidl]] for the speicfic target
### 3-implement the interface 

-stub : implementation of methods 

-Methods:implementation of the definition 

### 4-Expose Service to others :

expose >onBind()

