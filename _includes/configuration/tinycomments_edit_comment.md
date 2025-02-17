### `tinycomments_edit_comment`

The Comments plugin uses the `tinycomments_edit_comment` function to edit a comment.

The `tinycomments_edit_comment` function allows updating or changing existing comments and returns via the `done` callback once successful. Unrecoverable errors are communicated to {{site.productname}} by calling the `fail` callback instead.

The `tinycomments_edit_comment` function is given a request (req) object as the first parameter, which has these fields:

`conversationUid`
: The uid of the conversation the reply is targeting.

`commentUid`
: The uid of the comment to edit (it can be the same as `conversationUid` if editing the first comment in a conversation).

`content`
: The content of the comment to create.

`modifiedAt`
: The date the comment was modified.

The `done` callback should accept the following object:

```js
{
  canEdit: boolean, // whether or not the Edit succeeded
  reason: string? // an optional string explaining why the edit was not allowed (if canEdit is false)
}
```

For example:

```js
function edit_comment(ref, done, fail) {
  let conversationUid = ref.conversationUid;
  let commentUid = ref.commentUid;
  let content = ref.content;
  let modifiedAt = ref.modifiedAt;

  fetch(
    'https://api.example/conversations/' + conversationUid + '/' + commentUid,
    {
      method: 'PUT',
      body: JSON.stringify({ content: content, modifiedAt: modifiedAt }),
      headers: {
        Accept: 'application/json',
        'Content-Type': 'application/json',
      },
    }
  )
    .then((response) => {
      if (!response.ok) {
        throw new Error('Failed to edit comment');
      }
      return response.json();
    })
    .then((ref2) => {
      let canEdit = ref2.canEdit;
      done({ canEdit: canEdit });
    })
    .catch((e) => {
      fail(e);
    });
}

tinymce.init({
  selector: '#editor',
  plugins: 'tinycomments',
  tinycomments_mode: 'callback',
  tinycomments_create: create_comment,
  tinycomments_reply: reply_comment,
  tinycomments_edit_comment: edit_comment, // Add the callback to TinyMCE
  tinycomments_delete: delete_comment_thread,
  tinycomments_delete_all: delete_all_comment_threads,
  tinycomments_delete_comment: delete_comment,
  tinycomments_lookup: lookup_comment
});
```

