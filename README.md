# angular-weather
Hello! EVERYONE

This project was created by Jessica Sepulveda.

This is an app using the Ionic SDK with Angular Framework. 
This app was made possible with the help of: Ionic's magnificent documentation and lots of coffee.


To run the application: 
1.To install all packages necessary, in Terminal:  npm install -g@ionic/cli  
2.In terminal: cd weatherapi.angularionic
3.In terminal: ionic serve    to run application in localhost. browser window will open. 

About the Application: 

The application is a Weather App that helps the user prepare for their day by allowing them to 
check the daily weather by city. 

Tech: Angular, Ionic SDK, OpenMaps Library.
API: OpenMap API

Using a free API from openweather.org - specifically the Current Weather Data, 
I was able to get access for over 200,000 cities, which pulled in the data in JSON, XML, and HTML formats. 

1.The Weather Feature: 

--This is comprised of 2 main pages:

a. environment: which brings in the map API service (environment.ts) 
b. home: which manipulates the contents of that API service using a component home.page.ts.
        - home.html is where we see ionic and the angular directives make magic.

aa. (environment.ts) I included the API Key and API URL for the map inside the environment.ts -- similar to creating a service file. Since this was the only external API being called for this project. If multiple services were being used, I would've created a separate service file. 

bb. Inside (home.ts) file, I imported the HttpClient and calling HttpClient inside the constructor in order to obtain that external data.

I created the loadData() function and passed int the API URL and API KEY variables (which were declared above) in order to construct the URL and get the request from the OpenWeather API. I made sure to use the backticks to construct the URL we make a request to. 

When looking at the open weather API documentation, we can see: 
a1. the main[] parameters: temp, humidity, pressure, etc.
a2. the name[] parameters: for the searchbar to have its own name
a3. inside console -> JSON -> weather, we see that weather gives us an array at index 0[],  we can get all info
a4. list of weather condition codes with icons. From here we obtain the url provided to obtain the icon related to the weather. 

--Inside the (home.page.html), I was able to use the following parts learned in class: 
b1. ngModel binding: used to bind the values of my searchBar to obtain the input from the user when entering the city. 
b2. ngModelChange: to listen for changes to the input from the user. Since this is the output of the ngModel directive, it needs to be used together. 
b3. *ngIf: similar to the features provided by deBounceTime, I created a variable named loading to simplify the ability for the page to render after the used enters a city, if not (loading = true) and the page will be in "loading" status. 
    I used the ngIf in the HTML so that this directive could remove the HTML element for the entire div that contains the weather details. 
b4. pipes were used to fix the format of dates and temperatures which were originally in Kelvin. 
b5. ionic features were implemented all throughout. 





