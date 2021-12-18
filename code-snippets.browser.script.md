---
id: clXMbQ0VfYwnKppOUBknj
title: Script
desc: ''
updated: 1639847853081
created: 1639835046507
---

# Copy to clipboard

[MDN Interact with the clip board](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Interact_with_the_clipboard)

```js
function copy() {
  const textArea = document.createElement('textarea')
  textArea.value = result
  textArea.style.position = 'fixed'
  document.body.appendChild(textArea)
  textArea.focus()
  textArea.select()
  try {
    const successful = document.execCommand('copy')
    if (successful) {
      message.success('Copy Succeeded')
    } else {
      message.error("Can't copy to clip board")
    }
  } catch (err) {
    message.error(`Something went wrong.\n${err}`)
  }
  document.body.removeChild(textArea)
}
```

# Get selected text on a page

```js
window.getSelection().toString()
```
