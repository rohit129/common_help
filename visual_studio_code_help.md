**Visual Studio Code Help**
===========================

**Query 1:** ***Proxy setting in Visual Studio Code***

**Solution:**

Step 1: File > Preferences > Setting 

Step 2: Search Proxy. 

Step 3: Edit "settings.json"
```
  "http.proxy": "http://username:password@172.31.xx.xx:8080/"
```

[Extra Info Link-1](http://www.niranjankala.in/post/How-to-setup-Proxy-settings-in-Visual-Studio-Code), [Extra Info Link-2](https://stackoverflow.com/questions/70177216/visual-studio-code-error-while-fetching-extensions-xhr-failed)

Done!!


**Query 2:** ***How to CUDA enable device in debugger mode (Visual Studio Code)***

**Solution:**

Step 1: File > Preferences > Setting 

Step 2: Search launch. 

Step 3: Edit "launch.json". Add the following lines in the configuration
```
  "env": {"name":"CUDA_VISIBLE_DEVICES", "value":"0"}
```

[Stackoverflow Link](https://stackoverflow.com/questions/56757503/vscode-python-debugger-unrecognized-arguments)

Done!!
