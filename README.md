# Pytest With Appium ![pw](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)

<p align="center">
<img height="500" src="https://user-images.githubusercontent.com/95698164/171858189-9de5d3ef-f177-49ac-9de6-6edb3441740b.png">
</p>

<p align="center">
  <a href="https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/c/LambdaTest" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

_Appium is a tool for automating native, mobile web, and hybrid applications on iOS, Android, and Windows platforms. It supports iOS native apps written in Objective-C or Swift and Android native apps written in Java or Kotlin. It also supports mobile web apps accessed using a mobile browser (Appium supports Safari on iOS and Chrome or the built-in 'Browser' app on Android). Perform Appium automation tests on [LambdaTest's online cloud](https://www.lambdatest.com/appium-mobile-testing?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest)._

_Learn the basics of [Appium testing on the LambdaTest platform](https://www.lambdatest.com/support/docs/getting-started-with-appium-testing/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest)._

[<img height="53" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python)

## Table of Contents

- [Pre-requisites](#pre-requisites)
- [Run Your First Test](#run-your-first-test)
- [Executing The Tests](#executing-the-tests)

## Pre-requisites

Before you can start performing App automation testing with Appium, you would need to follow these steps:

- Install the latest Python build from the [official website](https://www.python.org/downloads/). We recommend using the latest version.
- Make sure **pip** is installed in your system. You can install **pip** from [here](https://pip.pypa.io/en/stable/installation/).
- Install pytest on your system with following pip command:

```bash
pip install pytest
```

### Clone The Sample Project

Clone the LambdaTest’s [LT-appium-python-pytest](https://github.com/LambdaTest/LT-appium-python-pytest) and navigate to the code directory as shown below:

```bash
git clone https://github.com/LambdaTest/LT-appium-python-pytest
cd LT-appium-python-pytest
```

### Setting Up Your Authentication

Make sure you have your LambdaTest credentials with you to run test automation scripts on LambdaTest. To obtain your access credentials, [purchase a plan](https://billing.lambdatest.com/billing/plans?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest) or access the [Automation Dashboard](https://appautomation.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest).

Set LambdaTest `Username` and `Access Key` in environment variables.

**For Linux/macOS:**

```bash
export LT_USERNAME=YOUR_LAMBDATEST_USERNAME \
export LT_ACCESS_KEY=YOUR_LAMBDATEST_ACCESS_KEY
```

**For Windows:**

```powershell
set LT_USERNAME=YOUR_LAMBDATEST_USERNAME `
set LT_ACCESS_KEY=YOUR_LAMBDATEST_ACCESS_KEY
```

### Upload Your Application

**Step-3:** Upload your **_iOS_** application (.ipa file) or **_android_** application (.apk file) to the LambdaTest servers using our **REST API**. You need to provide your **Username** and **AccessKey** in the format `Username:AccessKey` in the **cURL** command for authentication. Make sure to add the path of the **appFile** in the cURL request. Here is an example cURL request to upload your app using our REST API:

**Using App File:**

**Linux/macOS:**

```bash
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" \
--location --request POST 'https://manual-api.lambdatest.com/app/upload/realDevice' \
--form 'name="Android_App"' \
--form 'appFile=@"/Users/macuser/Downloads/proverbial_android.apk"'
```

**Windows:**

```powershell
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" -X POST "https://manual-api.lambdatest.com/app/upload/realDevice" -F "appFile=@"/Users/macuser/Downloads/proverbial_android.apk""
```

**Using App URL:**

**Linux/macOS:**

```bash
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" \
--location --request POST 'https://manual-api.lambdatest.com/app/upload/realDevice' \
--form 'name="Android_App"' \
--form 'url="https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk"'
```

**For Windows:**

```powershell
curl -u "YOUR_LAMBDATEST_USERNAME:YOUR_LAMBDATEST_ACCESS_KEY" -X POST "https://manual-api.lambdatest.com/app/upload/realDevice" -d "{"url":"https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk","name":"sample.apk"}"
```

**Tip:**

- If you do not have any **.apk** or **.ipa** file, you can run your sample tests on LambdaTest by using our sample :link: [Android app](https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_android.apk) or sample :link: [iOS app](https://prod-mobile-artefacts.lambdatest.com/assets/docs/proverbial_ios.ipa).
- Response of above cURL will be a **JSON** object containing the `App URL` of the format - <lt://APP123456789123456789> and will be used in the next step.

## Run Your First Test

Once you are done with the above-mentioned steps, you can initiate your first Python test on LambdaTest.

**Test Scenario:** Check out [conftest.py](https://github.com/LambdaTest/LT-appium-python-pytest/blob/master/conftest.py) file to view the sample test script for android and [ios.py](https://github.com/LambdaTest/LT-appium-python-pytest/blob/master/ios.py) for iOS.

### Configuring Your Test Capabilities

You can update your custom capabilities in test scripts. In this sample project, we are passing platform name, platform version, device name and app url (generated earlier) along with other capabilities like build name and test name via capabilities object. The capabilities object in the sample code are defined as:

**iOS:**

```python title="iOS(.ipa)"
    caps = {}
    caps["deviceName"] = "iPhone 11"
    caps["platformName"] = "iOS"
    caps["platformVersion"] = "14"
    caps["app"] = "lt://proverbial-ios"     #Enter the app (.ipa) url here
    caps["isRealMobile"] = True
    caps['build'] = build
    caps['name'] = test_name
    caps['project'] = project_name
```
**Android:**

```python title="Android(.apk)"
    caps = {}
    caps["deviceName"] = "Galaxy S21 5G"
    caps["platformName"] = "Android"
    caps["platformVersion"] = "11"
    caps["app"] = "lt://proverbial-android"   #Enter the app (.apk) url here
    caps["isRealMobile"] = True
    caps['build'] = build
    caps['name'] = test_name
    caps['project'] = project_name
```

**Info Note:**

- You must add the generated **APP_URL** to the `"app"` capability in the config file.
- You can generate capabilities for your test requirements with the help of our inbuilt **[Capabilities Generator tool](https://www.lambdatest.com/capabilities-generator/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest)**. A more Detailed Capability Guide is available [here](https://www.lambdatest.com/support/docs/desired-capabilities-in-appium/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest).

## Executing The Tests

- Install the dependencies with the following command.

```bash
pip install -r requirements.txt
```

- Go to the **tests** directory and run the following command to execute the tests. 

**Android:**

```bash
pytest test.py
```

**IOS:**

```bash
pytest test_ios.py
```

**Info Note:**
If you are unable to run the automation script with the above mentioned commands try using `python -m` before the given commands.

> Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on the [LambdaTest App Automation Dashboard](https://appautomation.lambdatest.com/build?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python-pytest).

> If you fail to run the tests, try creating virtual env and installing the dependencies in that environment to run the tests.
> Creating and activating a virtual environment

```
pip3 install virtualenv
virtualenv venv
source venv/bin/activate
```

## Additional Links

- [Advanced Configuration for Capabilities](https://www.lambdatest.com/support/docs/desired-capabilities-in-appium/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python)
- [How to test locally hosted apps](https://www.lambdatest.com/support/docs/testing-locally-hosted-pages/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python)
- [How to integrate LambdaTest with CI/CD](https://www.lambdatest.com/support/docs/integrations-with-ci-cd-tools/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python)

## Documentation & Resources :books:

Visit the following links to learn more about LambdaTest's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

- [LambdaTest Documentation](https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python)
- [LambdaTest Blog](https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python)
- [LambdaTest Learning Hub](https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python)

## LambdaTest Community :busts_in_silhouette:

The [LambdaTest Community](https://community.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At LambdaTest ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com/)

## About LambdaTest

[LambdaTest](https://www.lambdatest.com?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python) is a leading test execution and orchestration platform that is fast, reliable, scalable, and secure. It allows users to run both manual and automated testing of web and mobile apps across 3000+ different browsers, operating systems, and real device combinations. Using LambdaTest, businesses can ensure quicker developer feedback and hence achieve faster go to market. Over 500 enterprises and 1 Million + users across 130+ countries rely on LambdaTest for their testing needs.

### Features

- Run Selenium, Cypress, Puppeteer, Playwright, and Appium automation tests across 3000+ real desktop and mobile environments.
- Real-time cross browser testing on 3000+ environments.
- Test on Real device cloud
- Blazing fast test automation with HyperExecute
- Accelerate testing, shorten job times and get faster feedback on code changes with Test At Scale.
- Smart Visual Regression Testing on cloud
- 120+ third-party integrations with your favorite tool for CI/CD, Project Management, Codeless Automation, and more.
- Automated Screenshot testing across multiple browsers in a single click.
- Local testing of web and mobile apps.
- Online Accessibility Testing across 3000+ desktop and mobile browsers, browser versions, and operating systems.
- Geolocation testing of web and mobile apps across 53+ countries.
- LT Browser - for responsive testing across 50+ pre-installed mobile, tablets, desktop, and laptop viewports

[<img height="53" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python)

## We are here to help you :headphones:

- Got a query? we are available 24x7 to help. [Contact Us](mailto:support@lambdatest.com)
- For more info, visit - [LambdaTest](https://www.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=LT-appium-python)