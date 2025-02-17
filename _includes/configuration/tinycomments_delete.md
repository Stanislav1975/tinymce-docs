### `tinycomments_delete`

The `tinycomments_delete` function should asynchronously return a flag indicating whether the comment thread was removed using the `done` callback. Unrecoverable errors are communicated to {{site.productname}} by calling the `fail` callback instead.

The `tinycomments_delete` function is passed a (`req`) object as the first parameter, which contains the following key-value pair:

`conversationUid`
: The uid of the conversation the reply is targeting.

The `done` callback should accept the following object:

```js
{
  canDelete: boolean // whether or not the conversation can be deleted
  reason: string? // an optional string explaining why the delete was not allowed (if canDelete is false)
}
```

> **Note**: Failure to delete due to permissions or business rules is indicated by "false", while unexpected errors should be indicated using the "fail" callback.

For example:

```js
function delete_comment_thread(ref, done, fail) {
  let conversationUid = ref.conversationUid;
  fetch('https://api.example/conversations/' + conversationUid, {
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
  tinycomments_delete: delete_comment_thread, // Add the callback to TinyMCE
  tinycomments_delete_all: delete_all_comment_threads,
  tinycomments_delete_comment: delete_comment,
  tinycomments_lookup: lookup_comment
});
```

