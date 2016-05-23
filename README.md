
Capture
==================

  - [About](#about)
  - [Usage](#usage)
    - [IOS](#ios)
    - [Android](#android)
  - [Links](#license)


## About

Capture makes reporting bugs easy, which increases the productivity of your test engineers; standardized reporting enables your developers to focus on fixing the bug instead of finding and reproducing it.

Capture greatly improves your mobile testing processes.
Just shake the phone to report a bug and be amazed how
easy it can be.


## Usage

###IOS:

####Static Lib Requirements :

1) Turn off App Transportation Security

2) Target -> Build Settings -> Write “other linker flag” to search and add -ObjC -all_load to the related place

####To AppDelegate.m file

```
#import "MobvenBugReporter.h"
``` 
import in this way. 
```
didFinishLaunchingWithOptions
```
add the following code in the method above:

```
[MobvenBugReporter initializeAppSecret:@"1" appId:@"1" projectId:@"1" in- vokeTypes:@[@(Shake), @(FloatingButton)]];
```

####Usage of Embedded Framework//Objective C // ----------

1) Target-> General -> Embedded Binaries
Add MobvenBugKit.framework

2) Target -> Build Settings -> Write "Bitcode" to search and set the related place as 'YES'

3) Turn off App Transportation Security

####To the AppDelegate.m File:
```
#import <MobvenBugKit/MobvenBugKit.h>
didFinishLaunchingWithOptions
```
add the following code in the method above: 
```
[MobvenBugReporter initializeAppSecret:@"1" appId:@"1" projectId:@"1" in- vokeTypes:@[@(Shake), @(FloatingButton)]];
```

####Usage of Embedded Framework//Swift // —————

1) Target-> General -> Embedded Binaries
Add MobvenBugKit.framework

2) Target -> Build Settings -> Write "Bitcode" to Search and set the related place as 'YES'

3) Turn off App Transportation Security

####To the AppDelegate file:
```
import MobvenBugKit
didFinishLaunchingWithOptions
```
add the following code to the method above:
```
let types = [NSNumber(unsignedInteger:InvocationType.Shake.rawValue),NSNumber(un- signedInteger:InvocationType.FloatingButton.rawValue)]
MobvenBugReporter.initializeAppSecret("1", appId: "1", projectId: "1", in- vokeTypes:types)
```

###Android:
####1. To add aar file to project, copy aar file to lib folder

## Contributing

1. Create an issue and describe your idea
2. [Fork it] (https://github.com/skywinder/Github-Changelog-Generator/fork)
3. Create your feature branch (`git checkout -b my-new-feature`)
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Publish the branch (`git push origin my-new-feature`)
6. Create a new Pull Request
7. Profit! :white_check_mark:

*To test your workflow with changelog generator, you can use [test repo](https://github.com/skywinder/changelog_test/)*

## License

Github Changelog Generator is released under the [MIT License](http://www.opensource.org/licenses/MIT).
