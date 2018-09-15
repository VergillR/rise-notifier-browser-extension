# RISE notifications for Google Chrome and Chromium-based browsers

This is a browser extension for receiving RISE notifications for Google Chrome and other Chromium-based browsers, such as Opera and Vivaldi.
It checks up to 5 RISE addresses at the same time and it currently supports 7 languages (English, German, French, Spanish, Portuguese, Dutch and Russian).

Usage is straightforward: simply give 1 to 5 RISE addresses you want to follow.

### Summary
* Receive notifications for up to 5 RISE addresses in 7 different languages
* Near real-time notifications (<90 seconds) for incoming and outgoing transactions for each given RISE address
* Shows for each address the current amount of RISE and the name of the delegate (if the account holder of the address has voted)
* Shows current prices (RISE/USD and RISE/BTC) which are updated every 10 minutes
* On startup, shows notifications for any missed transactions when the browser was not running

### Installation
Normally, you can find and install extensions from the [Google Web Store](https://chrome.google.com/webstore/category/extensions). 
Some browsers, like Opera, may have their own store for extensions.

Alternatively, you can get the unpackaged extension by downloading this repo or cloning it with:

`git clone https://github.com/VergillR/rise-notifier-browser-extension`

And then adding the extension manually to the browser:
1. open Google Chrome / Opera / Vivaldi / any Chromium-based browser
2. enter "about://extensions" in the URL bar
3. enable "Developer Mode"
4. click "Load Unpacked"
5. select the extension's directory and click OK.

### Adding extra languages
To add an extra language:
1. make a new folder inside the directory */_locales*
2. rename the new folder to the correct [locale](https://developer.chrome.com/webstore/i18n#localeTable) for the language. For example, for Korean, the folder should be called *ko*
3. copy the file */_locales/en/messages.json* and paste it inside the new directory
4. translate and replace all values of _"message"_ with the translations; so, translating the English word _address_ is replacing the word _"address"_ behind the _"message"_ with the translation. For example, translating it into Korean looks like:

    ```json
    "address": {
        "message": "주소"
    }
  
5. the _"locale"_ and _"momentformat"_ are used by [Moment.js](http://momentjs.com/); the locale is usually the same as the locale from step 2. For Korean, it would look like:

    ```json
    "locale": {
        "message": "ko"
    },
    "momentformat": {
      "message": "D MMMM YYYY, HH:mm:ss"
    }

### Notes
This extension only works for Google Chrome and other Chromium-based browsers.

For Firefox: [click here](https://github.com/VergillR/rise-notifier-browser-extension-firefox)

For Microsoft Edge: [click here](https://github.com/VergillR/rise-notifier-browser-extension-edge)
