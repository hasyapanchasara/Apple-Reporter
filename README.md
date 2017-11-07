# Apple-Reporter
Apple Reporter to display sales &amp; finance reports from iTunes

- Used to fetch Sales / Finance report from Apple by using cronjob and command line
- Same like we do on itunesconnect.com

-------------------------------------------------------------------------------------------

# Purpose

(1) Get Sales / Financial reports from Apple

(2) Using command line, download report

(3) Parse it and save it in DB

(4) From DB, you can display report, graphs on admin or web interface

(5) Sales report provide total download

(6) Financial report provide Sales ( Revenue generated ) and Refund ( App refunds )

(7) Sales report can be use daily, weekly, monthly or any time interval

(8) Financial report reflect monthly

-------------------------------------------------------------------------------------------

# Terminal commands

(1)
Lion:Reporter bv$  java -jar Reporter.jar p=Reporter.properties m=Robot.XML Finance.getReport AppleID, US, Financial, 2016, 10

<?xml version="1.0" encoding="UTF-8" standalone="yes"?>


    Successfully downloaded AppleID_0716_US.txt.gz


(2)
Lion:Reporter bv$  java -jar Reporter.jar p=Reporter.properties m=Robot.XML Sales.getReport AppleID, US, Financial, 2016, 10

<?xml version="1.0" encoding="UTF-8" standalone="yes"?>

    201
    Invalid report type specified. Valid values include: Sales, Newsstand, Pre-order, Cloud, Event, Customer, Content, Station, Control, amEvent, amContent, amControl, amStreams, Subscription and SubscriptionEvent.


(3)
Lion:Reporter bv$  java -jar Reporter.jar p=Reporter.properties m=Robot.XML Finance.getReport AppleID, US, Sales, 2016, 10

<?xml version="1.0" encoding="UTF-8" standalone="yes"?>

    301
    Invalid report type specified. Valid values include: Financial, Match, Radio, RadioSummary, AppleMusic, AppleMusicSummary, News, and BeatsRadio.


(4) 
java -jar Reporter.jar p=Reporter.properties m=Robot.XML Sales.getReport AppleID, Sales, Summary, Daily, 20162811

-------------------------------------------------------------------------------------------

# Tools 

Reporter.propertiesReporter.jar

Using Reporter.properties

UserId= your apple account email address

Password= your apple account password

Mode=Robot.xml

-------------------------------------------------------------------------------------------

# Reference

https://help.apple.com/itc/appsreporterguide/#/itcbe21ac7db

SalesUrl=https://reportingitc-reporter.apple.com/reportservice/sales/v1

FinanceUrl=https://reportingitc-reporter.apple.com/reportservice/finance/v1
