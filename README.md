# Asset List Grabber

## What is this?

This is a simple script that will grab the author and asset name from the asset list on the [Asset Store](https://assetstore.unity.com/).
I made this, so that I could personally keep track of the assets I have purchased, and the authors of those assets, without having to dig through the menus on the asset store.

## Code Snippets

### Javascript (For exporting to Excel)

```javascript
// Feel free to change any of this.
var authorClassName = "_1x95x"; // This is the *Current* classname used by the author divs.
var assetClassName = "_161YN _30Ec_"; // This is the *Current* classname used by the asset divs.
// The seperator the code will use. Keep in mind, some assets use a dash in their name.
var rowSeparator = "$";
var columnSeparator = "#";


var authorList = document.getElementsByClassName(authorClassName);

var assetList = 
document.getElementsByClassName(assetClassName);

var completeString = "";

for(let i = 0; i < authorList.length && i < assetList.length; i++)
{
    completeString += (authorList[i].text + rowSeparator + assetList[i].textContent + columnSeparator);
}

console.log(completeString);
```

### Javascript (For easy PlainText

```javascript
// Feel free to change any of this.
var authorClassName = "_1x95x"; // This is the *Current* classname used by the author divs.
var assetClassName = "_161YN _30Ec_"; // This is the *Current* classname used by the asset divs.
// The seperator the code will use. Keep in mind, some assets use a dash in their name.
var rowSeparator = " || ";
var columnSeparator = "\n";


var authorList = document.getElementsByClassName(authorClassName);

var assetList = 
document.getElementsByClassName(assetClassName);

var completeString = "";

for(let i = 0; i < authorList.length && i < assetList.length; i++)
{
    completeString += (authorList[i].text + rowSeparator + assetList[i].textContent + columnSeparator);
}

console.log(completeString);
```

### Excel

```js
=TEXTSPLIT(A1; "$";"#";)
```

I advise you set the seperator to the same as the one used in the javascript code, and set the location (A1) to the cell containing the author and asset name.

## Instructions

1. Navigate to Unity Asset Store > My Assets.
2. Set the Total per page to 100.
3. Paste the javascript code above, into the console of your browser.
4. Execute the code.
5. Copy the output from the console. If you have more assets, load the next page and repeat.
6. Paste the output into a spreadsheet.
7. Apply the excel code above to the spreadsheet, to seperate the author and asset name.
8. Done!
