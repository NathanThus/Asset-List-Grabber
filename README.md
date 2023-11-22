# Asset-List-Grabber

## What is this?

This is a simple script that will grab the author and asset name from the asset list on the [Asset Store](https://assetstore.unity.com/).
I made this, so that I could personally keep track of the assets I have purchased, and the authors of those assets, without having to dig through the menus on the asset store.

## Code Snippets

### Javascript

```javascript
// Feel free to change any of this.
var authorClassName = "_1x95x"; // This is the *Current* classname used by the author divs.
var assetClassName = "_161YN _30Ec_"; // This is the *Current* classname used by the asset divs.
// The seperator the code will use. Keep in mind, some assets use a dash in their name.
var seperator = " || "; 


var authorList = document.getElementsByClassName(authorClassName);

var assetList = 
document.getElementsByClassName(assetClassName);

var completeString = "";

for(let i = 0; i < authorList.length && i < assetList.length; i++)
{
    completeString += (authorList[i].text + seperator + assetList[i].textContent + '\n');
}

console.log(completeString);
```

### Excel / Google Sheets

*Excel:*

```js
=TEXTSPLIT(A1;"|")
```

*Google Sheets:*

```js
=SPLIT(A1,"|")
```

I advise you set the seperator to the same as the one used in the javascript code, and set the location (A1) to the cell containing the author and asset name.

## Instructions

1. Paste the javascript code above, into the console of your browser.
2. Execute the code.
3. Copy the output from the console.
4. Paste the output into a spreadsheet.
5. Apply the excel code above to the spreadsheet, to seperate the author and asset name.
6. Done!
