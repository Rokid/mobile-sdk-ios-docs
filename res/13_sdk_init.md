# Mobile SDK 初始化

### 初始化

使用 Mobile SDK 之前必须要先初始化SDK，否则无法正常使用 Mobile SDK。

**注意:**

 1. 异步初始化RokidMobileSDK, 请确保初始化成功，否则其余API都会失败。
 2. **<font color=red size=3>appKey、appSecret、accessKey 请按照真实填写，否则会初始化失败。</font>**
 3. **<font color=red size=3>appKey、appSecret、accessKey 请到 https://account.rokid.com/#/setting/prove 中申请。</font>**
 4. **<font color=red size=3>appKey、appSecret、accessKey 线上、测服 是不一样的，如果需要使用 测服环境，请找 对接的项目经理 申请</font>**

**参数说明：**

| 字段         | 类型    | 必须？| 说明 |
| :---------  | --------- | :---: | --- |
| appKey | String | 是 | Rokid 发放的 appKey |
| appSecret | String | 是 | Rokid 发放的 appSecret |
| accessKey | String | 是 | Rokid 发放的 accessSecret |

**示例代码：**

Swift:

```swift
RokidMobileSDK.shared.initSDK(appKey: String,
                              appSecret: String,
                              accessKey: String,
                              complete: {(error: RKError) in 
                                         
                                         // SDK init 完成
                                         if (error != nil) {
                                             // ...
                                         };  
                                        
  })
```

Objc:

```objc
[RokidMobileSDK.shared initSDKWithAppKey:"xxx"
                                   appSecret:"xxx"
                                   accessKey:"xxx"
                                   completion:^(RKError * error) {
        NSLog(@"[SDK init] result = %@", error);
        
        // SDK init 完成
        if (!error) {
            NSLog(@"SDK init success");
        };
    }];
```

---

