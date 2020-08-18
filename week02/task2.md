
UTF-8 Encoding 函数
```js

function encodeUtf8(text) {
  let bytes = [];
  for(i = 0; i < text.length; i++) {
    bytes.push(text.charCodeAt(i));
  }

  return bytes;
}

function decodeUtf8(bytes) {
  let encoded = "";
  for(i = 0; i < bytes.length; i++) {
    encoded += String.fromCharCode(bytes[i]);
  }

  return encoded;
}


```