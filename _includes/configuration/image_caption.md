### `image_caption`

This option lets users enable captions for images. When this option is enabled the image dialog will have an extra checkbox called "Caption". When a user checks the checkbox the image will get wrapped in an HTML5 `figure` element with a `figcaption` inside it. The user will then be able to type caption content inside the editor.

**Type:** `Boolean`

**Default Value:** `false`

**Possible Values:** `true`, `false`

#### Example: Using `image_caption`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'image',
  menubar: 'insert',
  toolbar: 'image',
  image_caption: true
});
```

Below is an example of the HTML created when a user selects the caption checkbox.

```html
<figure class="image">
<img src="url" alt="" />
<figcaption>Caption</figcaption>
</figure>
```

Note that the `figure` element needs some custom CSS added to render properly. This is what we use in the internal `content.css` within {{site.productname}}, and can be overridden with your own custom [`content_css`]({{ site.baseurl }}/configure/content-appearance/#content_css) stylesheet.

```css
{% include css-codeblock/image-plugin-css.md %}
```
