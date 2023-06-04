# JS-Code-Snippets

## 1. JavaScript library that you can use to open a popup screen with a YouTube link on HTML websites

```javascript
// Create a function to open the popup screen
function openPopup(youtubeLink) {
  // Create a new window with specific dimensions
  const width = 800;
  const height = 600;
  const left = (window.innerWidth - width) / 2;
  const top = (window.innerHeight - height) / 2;
  const options = `width=${width},height=${height},top=${top},left=${left}`;

  // Open the YouTube link in the new window
  window.open(youtubeLink, 'popup', options);
}

// Example usage
const youtubeLink = 'https://www.youtube.com/watch?v=VIDEO_ID';
openPopup(youtubeLink);
```

In this code, we define the `openPopup` function that takes a `youtubeLink` parameter. It calculates the center position of the screen and opens a new window with the specified dimensions using `window.open`. The `youtubeLink` is opened in the new window.

To use this library in your HTML website, you need to include the JavaScript code in a `<script>` tag:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Popup Screen Example</title>
</head>
<body>
  <!-- HTML content -->

  <script>
    // Include the JavaScript library code here
    // ...

    // Call the openPopup function with your YouTube link
    const youtubeLink = 'https://www.youtube.com/watch?v=VIDEO_ID';
    openPopup(youtubeLink);
  </script>
</body>
</html>
```

Replace `'https://www.youtube.com/watch?v=VIDEO_ID'` with the actual YouTube link you want to open in the popup screen.

Note that modern web browsers often block popups by default, so the user may need to enable popups for your website or click on a browser notification to open the popup screen.
