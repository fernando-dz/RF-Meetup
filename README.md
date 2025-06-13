# Robot Framework Mobile Login Test Suite

This project contains a Robot Framework test suite designed to test a bad or negative login functionality of a mobile (Android) application using Appium.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Test Suite Overview](#test-suite-overview)
- [Running the Tests](#running-the-tests)
- [Test Cases](#test-cases)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

Before running the tests, ensure you have the following installed:

- [Python](https://www.python.org/downloads/) (version 3.9 or higher)
- [Robot Framework](https://robotframework.org/)
- [Appium](http://appium.io/)
- [AppiumLibrary](https://github.com/robotframework/AppiumLibrary)
- [Android SDK](https://developer.android.com/studio)
- [Node.js](https://nodejs.org/) (for Appium)

## Installation

1. Clone this repository:

   ```
   git clone https://github.com/yourusername/robot-framework-bad-login.git
   cd robot-framework-bad-login
#
2. Install the required Python packages:
   ```
   pip install robotframework
   pip install robotframework-appiumlibrary
#
3. Ensure Appium server is running:
   ```
   appium
#
4. Make sure your Android device is connected and recognized by ADB:
   ```
   adb devices
#
5. Install the application APK on your device:
   ```
   adb install path/to/your/app-debug.apk

## Test Suite Overview

The test suite is defined in the BadLogin-Tests.robot file and utilizes the following settings:
    
    *** Settings ***
    Library    AppiumLibrary
    Resource    ${CURDIR}/../BadLogin-Keys.robot

### Variables

The following variables are defined for the test suite:

    *** Variables ***
    ${REMOTE_URL}    http://localhost:4723/wd/hub
    ${PLATFORM}    Android
    ${PLATFORM_VERSION}    14
    ${DEVICE_NAME}    Android-Device-ID-Here
    ${APP_LOCATION}    ${CURDIR}/../APKs/app-debug.apk
    ${APP_ACTIVITY}    com.app.name.SplashActivity
    ${APP_PACKAGE}    com.app.name.Development
    ${AUTOMATION_NAME}    uiautomator2
    ${SETTINGS_PAGE}    Settings Present?
    ${UIAUTOMATOR2_SERVER_INSTALL_TIMEOUT}    50000ms
    
## Running the Tests

To execute the test suite, run the following command in your terminal:

    robot BadLogin-Tests.robot

## Test Cases

The following test case is included in the suite:

### Bad Login

- Description: Tests the application's response to invalid login data.
- Steps:
  1. Launch the application.
  2. Enter invalid data.

          *** Test Cases ***
          Bad Login    
              Launch
              Enter Invalid Data
          
## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue for any enhancements or bug fixes.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
