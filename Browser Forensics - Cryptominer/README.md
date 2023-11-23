# Tools used
* FTK Imager

## Answers
Question 1: How many browser-profiles are present in Google Chrome?
<br>Answer: `2`

As the question mentioned, we will analyze Google Chrome's browser data to identify the exisiting profiles. Typically, a 'Default' profile will come in with its default settings after Google installation,
however, users can add in additional profiles here. Hence, by analyzing the files, 2 profiles can be found, 'Default' and 'Profile1'.

<p align='center'>
  <img src='/images/crypto1.png' alt="crypto1">
</p>

<p align='center'>
  <img src='/images/crypto2.png' alt="crypto2">
</p>

Question 2: What is the name of the browser theme installed on Google Chrome?
<br>Answer: `Earth in Space`

By default, every Google browser theme will be saved in the Preferences file in 'Default'. 
In the file, we can grep/search the text 'theme' to obtain an id parameter. Judging by the id wording, its definitely an extension.

<p align='center'>
  <img src='/images/crypto3.png' alt="crypto3">
</p>

<p align='center'>
  <img src='/images/crypto4.png' alt="crypto4">
</p>

This ID (iiihlpikmpijdopbaegjibndhpgjmjfe) is basically the extension ID which can be found the the Extensions folder in 'Default'. 
Going through its json file (manifest.json), we can find the browser theme used.

<p align='center'>
  <img src='/images/crypto5.png' alt="crypto5">
</p>

<p align='center'>
  <img src='/images/crypto6.png' alt="crypto6">
</p>

Question 3: Identify the Extension ID and Extension Name of the cryptominer
<br>Answer: `egnfmleidkolminhjlkaomjefheafbbb, DFP Cryptocurrency Miner`

Question 4: What is the description text of this extension?
<br>Answer: `Allows staff members to mine cryptocurrency in the background of their web browser`

Remember the keyword here is EXTENSION, so we will look through each extension to find anything malicious. Going through the extensions, an extension was found with a javascript file called 'background.js'.
Looking at its json file, the description literally mentions mining cryptocurrency, WOW. Hence, its extension ID and name is recorded.

<p align='center'>
  <img src='/images/crypto7.png' alt="crypto7">
</p>

Question 5: What is the name of the specific javascript web miner used in the browser extension?
<br>Answer: `cryptoloot`

Question 6: How many hashes is the crypto miner calculating per second?
<br>Answer: `20`

Question 7: What is the public key associated with this mining activity?
<br>Answer: `b23efb4650150d5bc5b2de6f05267272cada06d985a0`

Question 5-7 can all be found in the cryptominer javascript file. 

<p align='center'>
  <img src='/images/crypto8.png' alt="crypto8">
</p>

Question 8: What is the URL of the official Twitter page of the javascript web miner?
<br>Answer: `twitter.com/CryptoLootMiner`

Do your OSINT!
