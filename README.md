# JS Code Snippets

## Open a popup screen with a YouTube link on HTML websites

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
*****

## Fetch any API 

```javascript
// Fetch data from an API
fetch('https://api.example.com/data')
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    console.log(data);
    // Process the retrieved data
  })
  .catch(error => {
    console.error('Error:', error);
    // Handle the error
  });
```

- Use the `fetch()` function to make a request to the specified URL (`https://api.example.com/data` in this case). 
- The `fetch()` function returns a promise that resolves to the `Response` object representing the server's response.
- Chain a `.then()` method to the promise, which takes a callback function to handle the successful response.
= Inside the callback function, check if the response was successful (`response.ok`). If not, throw an error.
- Call the `.json()` method on the response object to parse the response body as JSON. This method also returns a promise.
= Chain another `.then()` method to the promise, which takes a callback function to handle the parsed JSON data.
= Inside the callback function, access and process the retrieved data as needed.

If any errors occur during the process, the `.catch()` method is called with an error object. The error is logged to the console, and you can handle the error appropriately.

You can replace `https://api.example.com/data` with the actual API endpoint you want to fetch data from. Additionally, you can modify the code to handle different types of responses or error scenarios based on your specific requirements.
*****

## Cross blockchain bridging 

```javascript
class SriXchain {
  constructor(network) {
    this.network = network;
  }

  // Asset bridging function
  async bridgeAsset(sourceNetwork, targetNetwork, asset) {
    console.log(`Bridging ${asset} from ${sourceNetwork} to ${targetNetwork}`);

    // Implement your logic here for bridging the asset from the source network to the target network
    return new Promise((resolve, reject) => {

      // Simulating a successful bridging process
      resolve(`Asset ${asset} bridged from ${sourceNetwork} to ${targetNetwork}`);
    });
  }

  // Atomic swap function
  async atomicSwap(network1, asset1, network2, asset2) {
    console.log(`Performing atomic swap between ${network1} and ${network2}`);

    // Implement your logic here for atomic swaps between network1 and network2
    return new Promise((resolve, reject) => {

      // Simulating a successful atomic swap
      resolve(`Atomic swap complete: ${asset1} from ${network1} to ${network2} swapped with ${asset2}`);
    });
  }

  // Cross-chain communication protocol function
  async crossChainCommunication(sourceNetwork, targetNetwork, message) {
    console.log(`Sending message from ${sourceNetwork} to ${targetNetwork}: ${message}`);

    // Implement your logic here for cross-chain communication between sourceNetwork and targetNetwork
    return new Promise((resolve, reject) => {

      // Simulating a successful communication
      resolve(`Message sent from ${sourceNetwork} to ${targetNetwork}: ${message}`);
    });
  }

  // Function for setting the default network
  setDefaultNetwork(network) {
    this.network = network;
  }
}

## Usage example

const sriXchain = new SriXchain("Mainnet");
// Asset bridging example
sriXchain.bridgeAsset("Ethereum", "Binance Smart Chain", "ETH")
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

// Atomic swap example
sriXchain.atomicSwap("Ethereum", "ETH", "Binance Smart Chain", "BNB")
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

// Cross-chain communication example
sriXchain.crossChainCommunication("Ethereum", "Binance Smart Chain", "Hello!")
  .then((result) => console.log(result))
  .catch((error) => console.error(error));

// Set default network example
sriXchain.setDefaultNetwork("Testnet");
console.log(`Default network set to: ${sriXchain.network}`);
```
In this code, the `SriXchain` class represents the SriXchain library. It takes the `network` parameter in the constructor to specify the default network for the library.

The class provides three functions: `bridgeAsset`, `atomicSwap`, and `crossChainCommunication`. Each function simulates the respective cross-chain interaction with a delay using `setTimeout`. You can replace the implementation of these functions with the actual logic required for interacting with different blockchain networks.

To use the library, create an instance of `SriXchain` with the default network. Then, you can call the provided functions with the necessary parameters. Each function returns a promise that resolves when the operation is complete. You can handle the results and errors using `.then()` and `.catch()`.

Feel free to replace the placeholder implementation in each function with your own logic for interacting with blockchain networks. For example, you can use appropriate blockchain APIs or libraries to perform asset bridging, atomic swaps, or cross-chain communication.

Remember to include any required dependencies or import statements in your actual code before using the `SriXchain` class. Please note that the code provided is a simplified example and may need to be adapted to fit your specific use case and the blockchain networks you are working with. An additional function `setDefaultNetwork(network)` is added to the `SriXchain` class. This function allows you to set the default network for the library.

After creating an instance of `SriXchain`, you can call the `setDefaultNetwork(network)` function to set the default network. The updated default network value can be accessed using the `network` property of the `SriXchain` instance.

The example demonstrates how to use the `setDefaultNetwork(network)` function by setting the default network to "Testnet" and then logging the updated default network value.

Feel free to customize and extend the code according to your specific requirements.

## Scrap email addresses from any websites
```javascript
// HTML:
// <input id="urlInput" type="text" placeholder="Enter website URL">
// <button id="scrapeButton">Scrape Emails</button>
// <div id="output"></div>

// JavaScript:
function scrapeEmails() {
  const urlInput = document.getElementById('urlInput');
  const output = document.getElementById('output');

  const url = urlInput.value;
  if (!url) {
    output.innerHTML = 'Please enter a website URL.';
    return;
  }

  fetch(url)
    .then(response => response.text())
    .then(html => {
      const regex = /[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}/g;
      const emails = html.match(regex);

      if (emails && emails.length > 0) {
        output.innerHTML = '<h3>Email Addresses:</h3>' + emails.join('<br>');
      } else {
        output.innerHTML = 'No email addresses found on the webpage.';
      }
    })
    .catch(error => {
      output.innerHTML = 'An error occurred while scraping the webpage.';
      console.error(error);
    });
}

const scrapeButton = document.getElementById('scrapeButton');
scrapeButton.addEventListener('click', scrapeEmails);
```

To use this code snippet, you'll need to add the HTML code to your webpage and include the JavaScript code in a `<script>` tag or an external JavaScript file. The library retrieves the website URL entered by the user, sends a `fetch` request to that URL, and searches for email addresses using a regular expression. The results are then displayed in the `output` div element.

Please note that web scraping can be subject to legal restrictions and terms of service of the websites being scraped. It's important to ensure that you have the necessary permissions and adhere to ethical practices when scraping websites.

## Display IP address at bottom centre of website 
```javascript
// Create a function to fetch the IP address
function getIPAddress() {
  fetch('https://api.ipify.org/?format=json')
    .then(response => response.json())
    .then(data => {
      const ipAddress = data.ip;
      // Display the IP address at the bottom of the screen
      const ipAddressElement = document.createElement('div');
      ipAddressElement.textContent = `IP Address: ${ipAddress}`;
      ipAddressElement.style.position = 'fixed';
      ipAddressElement.style.bottom = '0';
      ipAddressElement.style.left = '0';
      ipAddressElement.style.padding = '10px';
      ipAddressElement.style.backgroundColor = '#000';
      ipAddressElement.style.color = '#fff';
      ipAddressElement.style.fontFamily = 'Arial, sans-serif';
      document.body.appendChild(ipAddressElement);
    })
    .catch(error => console.error(error));
}

// Call the function to get and display the IP address
getIPAddress();
```

This code uses the `fetch` API to retrieve the IP address from the ipify API in JSON format. It then creates a `div` element, sets its text content to the IP address, and applies some basic styling to make it visible at the bottom of the screen. Finally, the `div` element is appended to the `body` of the HTML document.
