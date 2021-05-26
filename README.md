# UFO Sightings

## Overview
The purpose of this project is to create a webpage that will read and display a table of UFO sightings.  Users can choose to filter the table by any or all these choices: date, city, state, country or shape of the object.  

## Project Set Up
The project uses 4 files and an image.
1. An HTML file for the webpage.  This file includes Bootstrap elements which help to provide structure and color to the page.  The main elements include:
   - A Header
   - Jumbotron
   - Text
   - Form element to hold a list of input boxes on which the user can choose to filter the data
   - Table element for the data
2. Cascading style sheet, CSS, is used to style two elements of the page:
   - The body color is set to #f7f7f7 which is Lynx White
   - The jumbotron uses the background image nasa.jpg, the image is set to cover the entire area of the element and the text inside aligned to the center
3. The data file which was provided for the project and contains an array of objects.  An example of an object is as follows:
```
{
    datetime: "1/1/2010",
    city: "benton",
    state: "ar",
    country: "us",
    shape: "circle",
    durationMinutes: "5 mins.",
    comments: "4 bright green circles high in the sky going in circles then one bright green light at my front door."
  }
```
4. The javascript file which provides the code that will do the following:
   - Detect a change to any of the filters in the form
   - Display the full listing of the data file
   - If a change is detected to a filter, update the display to show only data matching the criteria.
   - A __filters__ object holds the key of which filter was changed, ie date, city, state, country or shape.   The value is the user input.
   - The updated __filters__ object key and value is then used in to rewrite the table data.  The code to do that is here:
```
  function filterTable() {
    let filteredData = tableData;
   
    for (key in filters){
      filteredData = filteredData.filter(row => row[key] === filters[key]);
    };
  
    buildTable(filteredData);
  }
```

## Results:


Summary:

The summary addresses one drawback of this webpage (2 pt)

The search options are case sensitive.  Entering CA for California yields empty results.  Whereas ca shows all sightings in California.
There should be more information about the dates available for searching

The summary addresses two additional recommendations for further development (4 pt)
Sort by functions could be added to allow users to see columns sorted by date, city, state, country or shape
Add case sensitive tests so for example if users would enter CA for California it will pull up data with ca for California
