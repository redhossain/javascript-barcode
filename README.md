# Dynamsoft JavaScript Barcode SDK

Version 6.5.1

The repository aims to help developers get familiar with [Dynamsoft JavaScript Barcode SDK](https://www.dynamsoft.com/Products/barcode-recognition-javascript.aspx).

This SDK supports decoding **1D**, **PDF417**, **QR**, **DataMatrix**, and **Aztec**.

The supported data sources include `Blob`, `HTMLImageElement`, `HTMLVideoElement`, URL and more.

The `LocalizationResult`(like [C# LocalizationResult](https://www.dynamsoft.com/help/Barcode-Reader/class_dynamsoft_1_1_barcode_1_1_localization_result.html)) can be found in decoding results.

If you want the `nodejs` version, please visit [dbr webassembly](https://github.com/dynamsoft-dbr/webassembly).

## Online Demo

<img src="https://github.com/dynamsoft-dbr/javascript-barcode/raw/master/img/dbr-wasm-demo-scaning.jpg">

[Online Demo in Github](https://htmlpreview.github.io/?https://github.com/dynamsoft-dbr/javascript-barcode/blob/master/examples/decodeVideoWithSettings/barcode_reader_javascript.html)

[Online Demo in Dynamsoft](https://demo.dynamsoft.com/dbr_wasm/barcode_reader_javascript.html)

## Browser Compatibility

Firefox performs the best on both desktop and mobile.

| Browser | Version |
|-|-|
| Chrome | v57+ |
| Firefox | v52+ |
| Edge | v16+ |
| Safari* | v11+ |
| Internet Explorer | not supported |

WebAssembly compiles really slow in Safari for iOS according to our tests.

## Documentation

[Dynamsoft Barcode Reader JavaScript Edition Manual](https://www.dynamsoft.com/help/Barcode-Reader-wasm/index.html)

<!--[Guide](https://github.com/dynamsoft-dbr/javascript-barcode/blob/master/documents/guide-original.md)

[API Reference](https://github.com/dynamsoft-dbr/javascript-barcode/blob/master/documents/api-original.md)-->

## Hello World Sample

1. Copy the following code into an HTML file `index.htm`.

```html
<!DOCTYPE html>
<html>
<body>
    <script>
        // https://www.dynamsoft.com/CustomerPortal/Portal/TrialLicense.aspx
        BarcodeReader.licenseKey = 'LICENSE-KEY';
        let scanner = new BarcodeReader.Scanner({
            onFrameRead: results => {console.log(results);},
            onNewCodeRead: (txt, result) => {alert(txt);}
        });
        scanner.open().catch(ex=>{
            console.log(ex);
            alert(ex.message || ex);
            scanner.close();
        });
    </script>
</body>
</html>
```
2. Deploy the file to [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb).
3. Open the page in a web browser.

## Change log

### 6.5.1
Added video view for barcode scan.

### 6.4.1.3

Size of `wasm` is 3.41M.
The `dbr-6.4.1.3.wasm` size is now reduced to 3.41M.

### 6.4.1.1

Fixed a memory leak related to `mTimeout` in `RuntimeSettings`.

### 6.4.1.0

Built Dynamsoft Barcode Reader 6.4.1 to JS(WebAssembly) version.

Combined the normal and the mobile version into one.

### 6.3.0.2

Added built-in Worker support.

```js
// The default value is false. By setting this value to true to decode in another thread, therefore UI wouldn't get stuck.
dynamsoft.dbrEnv.bUseWorker = true;
```

### 6.3.0.1

Set `dbr-<version>.js`(stable) as the main branch.

Added `dbr-<version>.mobile.js`(smaller, compiles quicker, requires less memory, but not as stable) for mobile Safari.

### 6.3.0

Built Dynamsoft Barcode Reader 6.3.0 to JS(WebAssembly) version.

## Contact Us

If there is any questions, please feel free to contact <support@dynamsoft.com>.

