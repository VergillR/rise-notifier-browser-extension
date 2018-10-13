![alt text](https://github.com/VergillR/rise-notifier-browser-extension/blob/master/icons/riseicon_128.png "RISE logo extension")
# RISE notifications for Google Chrome and Chromium-based browsers
This is a browser extension for receiving RISE notifications for Google Chrome and other Chromium-based browsers, such as Opera and Vivaldi.
It checks up to 5 RISE addresses simultaneously; You do not have to be the owner of the given addresses, so you can give any address you like. The extension currently supports 7 languages (English, German, French, Spanish, Portuguese, Dutch and Russian).

Usage is straightforward: simply give 1 to 5 RISE addresses you want to follow. Notifications about transactions from or to a followed RISE address will be displayed within 60 seconds.

### Summary
* Receive notifications for up to 5 RISE addresses in 7 different languages
* Near real-time notifications (<60 seconds) for incoming and outgoing transactions for each given RISE address
* Shows basic public information for each address, such as the current amount of RISE and the name of the delegate (if the account holder of the address has voted)
* Shows current prices (RISE/USD and RISE/BTC)
* On startup, shows notifications for any missed transactions when the browser was not running

### Installation
Normally, you can find and install extensions from the [Google Web Store](https://chrome.google.com/webstore/category/extensions). 
Some browsers, like Opera, may have their own store for extensions.

Alternatively, you can get the unpackaged extension by downloading this repo or cloning it with:

`git clone https://github.com/VergillR/rise-notifier-browser-extension`

And then adding the extension manually to the browser:
1. open Google Chrome / Chromium / Opera / Vivaldi / Brave / any Chromium-based browser
2. enter *chrome://extensions* in the URL bar (replace *chrome* with the name of your browser if you do not use Chrome or Chromium, like *opera* or *vivaldi*)
3. enable "Developer Mode"
4. click "Load Unpacked"
5. select the extension's directory and click OK
6. disable "Developer Mode" (keep Developer Mode on if you want to debug the extension)


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


### Data source
The extension gets its information from a RISE node that is linked to the RISE network. Click [here](https://github.com/RiseVision/rise-node/wiki/How-To-Install-The-TypeScript-Core.-(-=1.0.0)) for more information and instructions to set up your own node. You can choose your data source in the extension's *Options* screen.


### Privacy
Privacy is important. This extension uses the local storage on the device it is installed on, solely for the purposes for displaying necessary, public information. It never collects or asks for personal data (e.g. secret passphrase, login information or clipboard data). Stored data is not tracked, recorded, collected, shared or sold to third parties. Only use trusted data sources to ensure your privacy. At any time, you can delete all data stored on the device in the extension's *Options*. The code is open source (MIT license) so it can be fully reviewed.


### Notes
This extension only works for Google Chrome and other Chromium-based browsers.

For Mozilla Firefox: [click here](https://github.com/VergillR/rise-notifier-browser-extension-firefox)

For Microsoft Edge: [click here](https://github.com/VergillR/rise-notifier-browser-extension-edge)
