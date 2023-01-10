# SmartLogs

[![CI Status](https://img.shields.io/travis/Hamza Mughal/SmartLogs.svg?style=flat)](https://travis-ci.org/Hamza Mughal/SmartLogs)
[![Version](https://img.shields.io/cocoapods/v/SmartLogs.svg?style=flat)](https://cocoapods.org/pods/SmartLogs)
[![License](https://img.shields.io/cocoapods/l/SmartLogs.svg?style=flat)](https://cocoapods.org/pods/SmartLogs)
[![Platform](https://img.shields.io/cocoapods/p/SmartLogs.svg?style=flat)](https://cocoapods.org/pods/SmartLogs)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Features

 1) create new log file everyday with current date name.
 2) compress zip and make password on it (optional).
 3) Delete old files depending on the number of days provided to by developer
 4) Display an alert which take textual input from user about the issue / bug they are facing
 5) Hide the report alert view if you dont want the end user comment
 6) The theme of alert view can be customizable
 7) The send-to email should be provided by developer
 8) A JSON file should also get attached with following information:
        -> Device manufacturer
        -> Device model
        -> OS installed on device
        -> Currently running app version
        -> Free storage space available

## Swift
## Initization 

        // call initilization in the app delegate 
        // initilization sdk
        
        SLog.shared.initilization()
        
        
## Write Logs to file 

        // Summary logs must write log into the files 
        SLog.shared.summaryLog(text: "Hello World!!")
        
        // Detail logs are optional to write in the file
        SLog.shared.detailLog(text: "detail log here", writeIntoFile: true)


## Setup log file
        
        // Set zip archive Password
        SLog.shared.setPassword(password: "Password12345")
        
        // set days for Logs Deletion
        SLog.shared.setDaysForLog(numberOfDays: 7)
        
        // delete logs files forcefully
        SLog.shared.deleteOldLogs(forcefullyDelete: true)
        
        // Attachment Files     
        SLog.shared.addAttachment(fileName: "icon", url: filePath, mimeType: "image/png")
        
        // set email
        SLog.shared.setEmail(text: "abc@xyz.com")
        
        // set email Subject
        SLog.shared.setSubjectToEmail(sub: "BUG REPORT ")
        

## Report Alert (end user UI)
        
        // set Title
        SLog.shared.setTitle(title: "Map App")
        
        // set main alert view background color
        SLog.shared.setMainBackgroundColor(backgroundColor: .yellow)
        
        // set place holder for the text views
        SLog.shared.setPlaceHolder(text: "Enter Your Bug Detail")
        
        // set final log file name which is going to be emailed
        SLog.shared.setLogFileName(text: "finalLog")
        
        
        //set nobe and line color
        SLog.shared.setKnobColor(color: .red)
        SLog.shared.setLineColor(color: .green)
                
        // set text view text, font name, font size, and text color
        SLog.shared.setTextViewBackgroundColor(backgroundColor: .brown)
        SLog.shared.setTextViewTextColor(color: .green)
        SLog.shared.setTextViewFont(fontName: "Marker Felt Thin")
        SLog.shared.setTextViewFontSize(fontSize: 17)
        
        // set title text, font name, font size and text color
        SLog.shared.setTitle(title: "Title Here")
        SLog.shared.setTitleFont(fontName: "Marker Felt Thin")
        SLog.shared.setTitleFontSize(fontSize: 22)
        SLog.shared.setTitleColor(color: .purple)

        // set send button view text, icon, font name, font size, and text color
        SLog.shared.setSendButtonText(text: "Send Button Text")
        SLog.shared.setSendBtnFont(fontName: "Marker Felt Thin")
        SLog.shared.setSendBtnFontSize(fontSize: 30)
        SLog.shared.setSendBtnTextColor(color: .green)
        SLog.shared.setSendButtonBackgroundColor(backgroundColor: .black)
        SLog.shared.setSendBtnImage(img: UIImage(named: "testImg")!)
        SLog.shared.hideSendBtnIcon(bool: true)

## Hide Show Report View

        // report alert view is true by default make the bool true 
        // if you want to hide the report view and open the mail directly 
        SLog.shared.hideReportDialogue(bool: false)
        
## Send Report

        // Send Report
        SLog.shared.sendReport(controller: self)
        
        
## Objective C Usage

        // import the pod file in .m file
        @import SmartLogs;
        
        // initilization sdk
        [[SLog shared] initilization ];

        // use the function of the pods
        [[SLog shared] summaryLogWithText:@"summary log"];
        [[SLog shared] detailLogWithText:@"detail log"];

        // call the alert view Controller
        [[SLog shared] sendReportWithController: self];
        

## Installation

SmartLogs is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'SmartLogs'
```

## Log Levels

The following log levels are supported:

 - `Debug`
 - `Info`
 - `Warning`
 - `Error`
 - `Message`

## Author

Whizpool, zzeeshan@gmail.com

 ## Let's Log

```swift
 // let's import the logging API package
import SmartLogs

 // initilization Sdk
SLog.shared.initilization()

 // we're now ready to use it
 // summary log is used to print in console and it will also write the log into file 
SLog.shared.summaryLog(text: "Hello World!!")

 // detail log is used to print in console and it will also write the log into file (optional)
SLog.shared.detailLog(text: "Hello World!!", writeIntoFile: false)
```

# Output

```
2022-03-02 15:12:19.507 Hello World!!

```

## License

SmartLogs is available under the MIT license. See the LICENSE file for more info.
