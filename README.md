# from Quill ImageHandler Module
because Quill ImageHandler has some issues, when copied content that contains image both text, it will upload above all with a single image,image and text merge to a single image, no text part;
its not too good. then, i add a logic,if it contain image and text. it will stop upload function, we can upload image by upload buttons at the top toolbar。

![Image](/static/exp.png)
```bash
npm install quill-image-upload-2 --save
```

```javascript
import Quill from "quill";
import ImageUpload2 from "quill.imageUpload.js";

Quill.register("modules/imageUpload2", imageUpload2);

const quill = new Quill(editor, {
  // ...
  modules: {
    // ...
    imageUpload2: {
      upload: (file) => {
        return new Promise((resolve, reject) => {
          setTimeout(() => {
            resolve(
              "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/JavaScript-logo.png/480px-JavaScript-logo.png"
            );
          }, 3500);
        });
      },
    },
  },
});


> balabala

see [Quill ImageHandler]('https://github.com/NoelOConnell/quill-image-uploader')  

Quill ImageHandler is below :  

A module for Quill rich text editor to allow images to be uploaded to a server instead of being base64 encoded.
Adds a button to the toolbar for users to click, also handles drag,dropped and pasted images.

## Demo

![Image of Yaktocat](/static/quill-example.gif)

### Install

Install with npm:

```bash
npm install quill-image-uploader --save
```

### Webpack/ES6

```javascript
import Quill from "quill";
import ImageUpload from "quill.imageUpload.js";

Quill.register("modules/imageUpload", imageUpload);

const quill = new Quill(editor, {
  // ...
  modules: {
    // ...
    imageUpload: {
      upload: (file) => {
        return new Promise((resolve, reject) => {
          setTimeout(() => {
            resolve(
              "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/JavaScript-logo.png/480px-JavaScript-logo.png"
            );
          }, 3500);
        });
      },
    },
  },
});
```

### Quickstart (React with react-quill)

React Example on [CodeSandbox](https://codesandbox.io/s/react-quill-demo-qr8xd)

### Quickstart (script tag)

Example on [CodeSandbox](https://codesandbox.io/s/mutable-tdd-lrsvh)

```javascript
// A link to quill.js
<script src="/dist/quill.js"></script>
<script src="/dist/quill.imageUpload.min.js"></script>

Quill.register("modules/imageUpload", imageUpload);

var quill = new Quill(editor, {
  // ...
  modules: {
    // ...
    imageUpload: {
      upload: file => {
        return new Promise((resolve, reject) => {
          setTimeout(() => {
            resolve(
              "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/JavaScript-logo.png/480px-JavaScript-logo.png"
            );
          }, 3500);
        });
      }
    }
  }
});
```
