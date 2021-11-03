# List of Circulating Currencies

The JSON file lists all circulating currencies (currently 172 currencies) in the format below. Feel free to update and correct.

# JSON file description

The file contains the ISO 4217 3-letter currency codes as the property and the parameters as the property values which are further broken down into key/value pair for easy pickup.

| object property  |  Description |  
|---|---|
|name          | The full name of the currency|
|demonym       | The adjective (demonym) of the curries|
|majorSingle   | The currency major unit name in singular form|
|majorPlural   | The currency major unit name in plural form|
|ISOnum        | The ISO 4217 number of the currency|
|symbol        | The currency symbol in Latin form as most internationally used.|
|symbolNative  | The currency symbol in native language form|
|minorSingle   | The currency minor unit name in singular form|
|minorPlural   | The currency minor unit name in plural form|
|ISOdigits     | The number of digits after the decimal separator in accordance with ISO 4217|
|decimals      | The number of decimal places for the minor unit|
|numToBasic    | The total number of minor units in a major unit|


# Alternative Array List

The file currencyArray.js provides a shorter compact list using an array with the same parameters except for the full name. However, the full name can be made from the rest of the array data.

# Notes

## Why separate demonym
A separate entry is made for the demonym so flexibility is given to use the names of the Major and Minor units without the country name if needed.

# Examples

## Example 1: Read full information of a currency using its ISO code

```javascript

let currencyList = {..... } // the full list as provided in this repo

console.log(currencyList.USD);

//======================
// output
//======================
{
  name: 'United States Dollar',
  demonym: 'US',
  majorSingle: 'Dollar',
  majorPlural: 'Dollars',
  ISOnum: 840,
  symbol: '$',
  symbolNative: '$',
  minorSingle: 'Cent',
  minorPlural: 'Cents',
  ISOdigits: 2,
  decimals: 2,
  numToBasic: 100
}

```


## Example 2: Use single and plural with demonym


```javascript
let MyCurrecy = "USD";
let value = 3;
let demonym = currencyList[MyCurrecy].demonym;

if (value >1) {
console.log("The value is "+value+" "+demonym + " " + currencyList[MyCurrecy].majorPlural);
} else {
console.log("The value is "+value+" "+demonym + " " + currencyList[MyCurrecy].majorSingle);
}


//======================
\\ output
//======================

The value is 3 US Dollars
```


## Example 3: Use single and plural without demonym


```javascript
let MyCurrecy = "INR";
let value = 3;

if (value >1) {
console.log("The value is "+value+" "+ currencyList[MyCurrecy].majorPlural);
} else {
console.log("The value is "+value+" "+ currencyList[MyCurrecy].majorSingle);
}

//======================
\\ output
//======================

The value is 3 Rupees
```


# History:

03/11/2021 : Minor corrected JOD numToBasic corrected from 100 to 1000

15/10/2021 : Post to GitHub

15/05/2020 : Added Abkhazian Apsar and Artsakh Dram

30/01/2020 :  Five more currencies:

             EHP (Sahrawi Peseta)
             FOK (Faroese Króna)
             GGP Guernsey Pound
             IMP Manx Pound
             JEP Jersey Pound
             KID Kiribati Dollar
             PND Pitcairn Islands Dollar
             PRB Transnistrian Ruble
             SLS Somaliland Shilling
             TVD Tuvaluan Dollar
             VED Venezuelan bolívar digital

13/10/2019 : Added separate demonym for better flexibility

22/08/2019 : Initial list
