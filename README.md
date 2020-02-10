## Generate and encrypt payloads

This is a module for generating, encrypting and decrypting payloads for your app.

### Usecases

Your app (eg Electron) needs custom frontend updates that could be applied seamlessly.

```js
const Vault = require('encrypt-payloads')

const safe = new Vault('vault.dat', 'your-password')

safe.zip('frontend_folder')
  .then(res => safe.hashZip('frontend_folder.zip')) //698fc0a07263a530f66a65d0470ff37b725ec16062bd060bcf8a4a645da27885
  .then(r => safe.encryptAsync('frontend_folder')) //‘!ÓN `›a¡xRÁnz£ûÀ∏wK=ú©ÒF)cîø…Z˘∑?c˘ Ë$s
  .then(r => safe.decryptAsync()) //698fc0a07263a530f66a65d0470ff37b725ec16062bd060bcf8a4a645da27885
```
