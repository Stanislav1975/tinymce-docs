### `tinycomments_delete_all`

The `tinycomments_delete_all` function should asynchronously return a flag indicating whether all the comment threads were removed using the `done` callback. Unrecoverable errors are communicated to {{site.productname}} by calling the `fail` callback instead.

The `tinycomments_delete_all` function is given a request (req) object as the first parameter with no fields.

The `done` callback should accept the following object:

```js
{
  canDelete: boolean, // whether or not all conversations can be deleted
  reason: string? // an optional string explaining why the deleteAll was not allowed (if canDelete is false)
}
```

> **Note**: Failure to delete due to permissions or business rules should be indicated by `canDelete: false`, while unexpected errors should be indicated using the `fail` callback.

For example:

```js
function delete_all_comment_threads(_req, done, fail) {
  fetch('https://api.example/conversations', {
    method: 'DELETE',
  }).then((response) => {
    if (response.ok) {
      done({ canDelete: true });
    } else if (response.status === 403) {
      done({ canDelete: false });
    } else {
      fail(new Error('Something has gone wrong...'));
    }
  });
}

tinymce.init({
  selector: '#editor',
  plugins: 'tinycomments',
  tinycomments_mode: 'callback',
  tinycomments_create: create_comment,
  tinycomments_reply: reply_comment,
  tinycomments_edit_comment: edit_comment,
  tinycomments_delete: delete_comment_thread,
  tinycomments_delete_all: delete_all_comment_threads, // Add the callback to TinyMCE
  tinycomments_delete_comment: delete_comment,
  tinycomments_lookup: lookup_comment
});
```

