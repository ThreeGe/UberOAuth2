# NetworkEye
[![Pod Version](http://img.shields.io/cocoapods/v/NetworkEye.svg?style=flat)](http://cocoadocs.org/docsets/NetworkEye/)
[![Pod Platform](http://img.shields.io/cocoapods/p/NetworkEye.svg?style=flat)](http://cocoadocs.org/docsets/NetworkEye/)
[![Pod License](http://img.shields.io/cocoapods/l/NetworkEye.svg?style=flat)](https://opensource.org/licenses/MIT)


[README 中文](https://github.com/coderyi/NetworkEye/blob/master/README_Chinese.md)

NetworkEye,a iOS network debug library,It can monitor HTTP requests within the App and displays information related to the request.

It can be detected HTTP request include web pages, NSURLConnection, NSURLSession, AFNetworking, third-party libraries, third-party SDK ,and so on. very convenient and practical. 

I created a google group，this group is for general discussion NetworkEye
,welcome to join,[https://groups.google.com/d/forum/networkeye](https://groups.google.com/d/forum/networkeye)

if you use NetworkEye, you can add it in here,[Who-Uses-NetworkEye](https://github.com/coderyi/NetworkEye/wiki/Who-Uses-NetworkEye)

welcome to new pull request,that fix bug,add new features,add support other platform.and welcome to [new issues](https://github.com/coderyi/NetworkEye/issues).

#### Podfile

```ruby
platform :ios, '7.0'
pod 'NetworkEye', '~> 1.0'
```


####Instruction
Note：Use Network Eye in DEBUG mode

add the code in AppDelegate.m   
<pre>
#import "NEHTTPEye.h"
#if defined(DEBUG)||defined(_DEBUG)
    [NEHTTPEye setEnabled:YES];
#endif
</pre>

you can use a double tap or shake device to call out the monitoring data interface

NEHTTPEyeViewController

You can also use the following code present out directly
<pre>
#if defined(DEBUG)||defined(_DEBUG)
    NEHTTPEyeViewController *vc=[[NEHTTPEyeViewController alloc] init];
    [self presentViewController:vc animated:YES completion:nil];
#endif
</pre>
In NEHTTPEye.h there are two parameters you can configure that is the default password of database is "networkeye" ,and by default set,you can save 300 requests.


the database name is networkeye.sqlite,and stored in the cache directory.

<pre>
#define kSQLitePassword @"networkeye"

#define kSaveRequestMaxCount 300
</pre>

you can change it use NEHTTPModelManager
<pre>
    [NEHTTPModelManager defaultManager].saveRequestMaxCount=300;
    [NEHTTPModelManager defaultManager].sqlitePassword=@"networkeye";
</pre>
NetworkEye rely FMDB and SQLCipher。
FMDB be used to store data，SQLCipher be used to encrypt the database。

Monitoring data interface supports some search conditions ,it is URL，statusCode，HTTPMethod，MIMEType。
####Preview
the monitor data interface of NetworkEye：

<img  src="https://raw.githubusercontent.com/coderyi/NetworkEye/master/NetworkEye/Resources/networkeye1_3.png" width="320" height="570">

<img  src="https://raw.githubusercontent.com/coderyi/NetworkEye/master/NetworkEye/Resources/networkeye2.png" width="320" height="570">

<img  src="https://raw.githubusercontent.com/coderyi/NetworkEye/master/NetworkEye/Resources/networkeye3.png" width="320" height="570">



#### Licenses

All source code is licensed under the [MIT License](https://github.com/coderyi/NetworkEye/blob/master/LICENSE).

####Contributors

thanks!

[Xi Lin](https://github.com/xilin)

[Zhu Lida](https://github.com/zld)

[Jackrex](https://github.com/jackrex)
