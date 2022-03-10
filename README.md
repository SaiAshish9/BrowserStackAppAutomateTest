1. Setup 

```
Download test-suite.zip file and also tha .ipa file
```

2. Upload your app 

```
curl -u "csservice_5kdSJB:NsnDysS83Jv81pxXctMz" \
-X POST "https://api-cloud.browserstack.com/app-automate/xcuitest/v2/app" \
-F "file=@/Users/saiashishdarapureddy/Desktop/folders/projects/browserStackAppAutomate/BrowserStack-SampleApp.ipa"
```

```
{"app_name":"BrowserStack-SampleApp.ipa","app_url":"bs://06c242df93376aeea2f2aab592b8e6b68efd8cb7","app_version":"1.0","app_id":"06c242df93376aeea2f2aab592b8e6b68efd8cb7","uploaded_at":"2022-03-10 07:40:09 UTC","expiry":"2022-04-09 07:40:09 UTC"}%
```

3. Upload your test-suite 

```
curl -u "csservice_5kdSJB:NsnDysS83Jv81pxXctMz" \
-X POST "https://api-cloud.browserstack.com/app-automate/xcuitest/v2/test-suite" \
-F "file=@/Users/saiashishdarapureddy/Desktop/folders/projects/browserStackAppAutomate/BrowserStack-SampleXCUITest-v2.zip"
```

```
{"test_suite_name":"BrowserStack-SampleXCUITest-v2.zip","test_suite_url":"bs://85cee0c02c5373726a024fc025127faa5954fe30","test_suite_id":"85cee0c02c5373726a024fc025127faa5954fe30","uploaded_at":"2022-03-10 07:46:42 UTC","expiry":"2022-04-09 07:46:42 UTC","framework":"xcuitest"}%
```

4. Execute XCUI tests 

```
curl -u "csservice_5kdSJB:NsnDysS83Jv81pxXctMz" \
-X POST "https://api-cloud.browserstack.com/app-automate/xcuitest/v2/build" \
-d '{"app": "bs://06c242df93376aeea2f2aab592b8e6b68efd8cb7", "testSuite": "bs://85cee0c02c5373726a024fc025127faa5954fe30",  "devices": ["iPhone 13 Pro-15"]}' \
-H "Content-Type: application/json" 
```

```
{"message":"Success","build_id":"f67863e49db5c30e049cc049296217b09397b47d"}
```

5. Viewing test results 

```
https://app-automate.browserstack.com/dashboard/v2/quick-start/get-started#introduction ( Dashboard )

OR

https://www.browserstack.com/docs/app-automate/api-reference/xcuitest/overview ( REST API )
```

