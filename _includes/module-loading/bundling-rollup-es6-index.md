1. Add the {{site.productname}} assets and configuration into the project and provide a target element to initialize the editor.

    Example `src/index.js`

    ```js
    import * as editor from './editor';

    const parent = document.createElement('p');

    function editorArea() {
      const element = document.createElement('textarea');
      element.id = 'editor';
      return element
    }

    parent.appendChild(editorArea());
    document.body.appendChild(parent);

    editor.render();
    ```

    Example `demo.html`

    ```html
    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>TinyMCE Rollup Demo</title>
        <link rel="stylesheet" href="main.bundle.css">
      </head>
      <body>
        <h1>TinyMCE Rollup Demo</h1>
        <script src="main.bundle.js"></script>
      </body>
    </html>
    ```