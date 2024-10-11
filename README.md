# testing-browser
This is a simple, configurable JSON file, with predefined attributes, such as Browser type, separate user folder that isolates it from the default Chrome user AppData folder. 
It can be used with Edge, Chrome and Firefox

### Advantages
- No need for the incognito mode
- No inherited extension that make testing difficult
- Simple and configurable in the JSON file

### How to use
- open the "launch.json" in your IDE, e.g. VS Code
- change the browser type for your favourite one
- configure arguments
- use VS Code debugger to open your isolated browser


# Additional information 
Google Chrome has a wide variety of command-line flags (also called runtime arguments) that allow you to configure the browser’s behavior, debug, or run experiments. These flags can be useful for debugging, automation, performance tuning, and more.

Here’s a list of some commonly used and important Chrome command-line flags. Keep in mind that Chrome has many more, but these are often the most relevant ones for development and debugging.

Commonly Used Chrome Command-Line Flags:

## Basic Settings:

`--disable-popup-blocking`: Disables the built-in pop-up blocker.  
`--incognito`: Starts Chrome in incognito mode (no history, cookies, etc.).  
`--start-maximized`: Opens the browser in a maximized window.  
`--no-default-browser-check`: Disables the prompt asking to set Chrome as the default browser.  
`--disable-extensions`: Disables all installed Chrome extensions.  
`--disable-features=DarkMode`: Disables Chrome's dark mode feature.  
`--force-dark-mode`: Forces Chrome to use dark mode regardless of the OS theme.  
`--disable-notifications`: Disables all desktop notifications.  
`--disable-infobars`: Disables the “Chrome is being controlled by automated software” infobar.  

## User Profile and Data:  

`--user-data-dir=<path>`: Specifies the directory where Chrome should store user data (profile, cookies, etc.). Useful for isolating a testing environment.  
`--profile-directory=<profile_name>`: Launches Chrome using a specific profile.  

## Debugging and Remote Automation:  

`--remote-debugging-port=<port>`: Enables Chrome to be remotely debugged on the specified port (e.g., --remote-debugging-port=9222).  
`--headless`: Runs Chrome in headless mode (no GUI). Great for automation or running tests.  
`--disable-gpu`: Disables GPU hardware acceleration. Useful for running headless Chrome on systems without a GPU.  
`--enable-logging`: Enables logging to the console or a file.  
`--v=<log_level>`: Sets the verbosity of logging (--v=1, --v=2, etc.).  

## Networking and Connectivity:

`--proxy-server=<server_url>`: Configures Chrome to use a specific proxy server.  
`--no-proxy-server`: Disables the use of any proxy server.  
`--proxy-bypass-list=<list>`: Specifies a comma-separated list of hosts to bypass the proxy server.  
`--disable-web-security`: Disables the same-origin policy (useful for testing cross-origin requests locally, but a security risk in production).  
`--allow-running-insecure-content`: Allows loading of content over HTTP even when the site itself is loaded over HTTPS.  

## Performance and Benchmarking:  
  
`--disable-gpu-vsync`: Disables GPU-based vsync. Useful for benchmarking purposes.  
`--disable-accelerated-2d-canvas`: Disables GPU acceleration for 2D canvas rendering.  
`--enable-precise-memory-info`: Provides more detailed memory usage statistics.  
`--enable-benchmarking`: Enables extra benchmarking options.  

## Security and Privacy:  
  
`--no-sandbox`: Disables the Chrome sandbox (not recommended for regular use, only for specific testing).  
`--disable-web-security`: Disables web security features such as the same-origin policy. Only for development, as it poses serious security risks.  
`--allow-file-access-from-files`: Allows file access from local file URLs. Useful for debugging local files but can be risky.  
`--disable-background-networking`: Prevents Chrome from making network requests (for extensions, etc.) that are not explicitly triggered by the user.  

## Experimental and Feature Flags:  
  
`--enable-experimental-web-platform-features`: Enables experimental web features that are not yet fully rolled out in Chrome.  
`--enable-features=<feature1>,<feature2>`: Enables specific experimental features (comma-separated list of features).  
`--disable-features=<feature1>,<feature2>`: Disables specific features (e.g., --disable-features=DarkMode).  
`--enable-quic`: Enables the QUIC protocol, an experimental transport layer network protocol.  
`--enable-spdy4`: Enables SPDY/4, an experimental networking protocol.  

## Window and Display:  

`--window-size=<width>,<height>`: Sets the initial window size of the browser (e.g., --window-size=1920,1080).  
`--window-position=<x>,<y>`: Sets the initial position of the browser window.  
`--kiosk`: Runs Chrome in full-screen kiosk mode.  
`--app=<url>`: Launches Chrome as a standalone app window with the specified URL.  

## Media and Audio:  
  
`--mute-audio`: Mutes all audio output from the browser.  
`--disable-webgl`: Disables WebGL, the API used for rendering 3D graphics.  
`--autoplay-policy=no-user-gesture-required`: Allows autoplay of audio and video without requiring user interaction.  

## Others:  
  
`--disable-dev-shm-usage`: By default, Chrome uses /dev/shm (shared memory) for fast storage. This flag forces Chrome to not use shared memory, which can be useful when running Chrome inside Docker containers.  
`--crash-dumps-dir=<path>`: Specifies where to save crash dumps.  
`--disable-background-timer-throttling`: Disables throttling of background tasks in Chrome, which can improve performance for certain tasks like automated testing.  

### How to Use Command-Line Flags:  

## Windows:  
  
Create a shortcut to chrome.exe.  
Right-click the shortcut, select Properties.  
In the Target field, after chrome.exe, add the desired flags. Example:  
less  
Copy code  
```cmd
"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --disable-popup-blocking --incognito
```

## MacOS/Linux:  
  
Open a terminal and type:  
`css`
Copy code  
```cmd
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --disable-popup-blocking --incognito
```

## Comprehensive List:  
For a comprehensive and up-to-date list of Chrome flags, you can explore:  
   
Chrome URL: chrome://flags/ in your browser.  
Source code on the Chromium repository.  
This list is not exhaustive, but it covers the most commonly used and useful flags for developers and testers. You can combine these flags based on your specific needs for testing, debugging, or performance tuning.  
    
