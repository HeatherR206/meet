# Meet app using React + Vite

A progressive web app with the ability to work offline and a serverless backend
developed using a TDD technique.

## Test Cases

### **User Stories**

```

Feature 1: Filter Events By City

As a user,   
I should be able to filter events by city    
So that I can see what events are available for the current location I'm in.

```

```

Feature 2: Show/Hide Event Details

As a user,
I should be able to show or hide event details
So that I can toggle between a detailed single event or a longer list of events.

```

```

Feature 3: Specify Number of Events

As a user,
I should be able to specify the number of events I see
So that I can view a manageable number of events.

```

```

Feature 4: Use the App When Offline

As a user,
I should be able to use the app offline
So that I can use the app without worrying about an internet connection.

```

```

Feature 5: Add an App Shortcut to the Home Screen

As a user,
I should be able to add a shortcut to the app on my home screen
So that I can launch the app directly from my device.

```

```

Feature 6: Display Charts Visualizing Event Details

As a user,
I should be able to see charts visualizing event details
So that I can pinpoint event details in multiple cities at a glance.

```

### **Gherkin Scenarios**

```

Feature 1: Filter Events By City

Scenario 1: When the user hasn’t searched for a city, show upcoming events from all cities. 
Given the user has not searched for any city
When* the user opens the app
Then the user will see a list of all upcoming events


Scenario 2: Users should see a list of suggestions when they search for a city. 
Given the user was on the main page
When the user types “Ber” into the city search field
Then the user will see a list of city suggestions  that match “Ber”


Scenario 3: The user can select a city from the suggested list. 
Given the user was typing “Berlin” in the city search field 
And the list of suggested cities is displayed
When the user selects “Berlin, Germany” from the list
Then their city should be set to “Berlin, Germany”
And the user should see a list of upcoming events in  “Berlin, Germany”

```

```

Feature 2: Show/Hide Event Details

Scenario 1: An event element is collapsed by default. 
Given the user has opened the app
When the list of upcoming events is displayed
Then each event element should be collapsed
And the user should see only minimal event details
And a “Show Details” button should be visible


Scenario 2: Users can expand an event to see details.
Given the event element is collapsed
When the user clicks the “Show Details” button
Then the event element should expand
And the user should see the event description and additional details
And the button text should change to “Hide Details”


Scenario 3: User can collapse an event to hide details. 
Given an event element is currently expanded
When the user clicks the “Hide Details” button
Then the event element should collapse 
And the addition details should be hidden from view

```

```
Feature 3: Specify Number of Events 
Scenario 1: When the user hasn’t specified a number, 32 events are shown by default.
Given the user has the opened the app
When the user has not specified a number of events
Then the “Number of Events” field should display 32
And the list should display a maximum of 32 events


Scenario 2: Users can change the number of events displayed. 
Given the user is on the main page
When the user enters “15” in the “Number of Events” field
Then the “Number of Events” field should update to display exactly 20 events

```

```

Feature 4: Use the App When Offline 

Scenario 1: Show cached data when there’s no internet connection. 
Given the user has previously loaded event data while  online
And the device has on internet connection 
When the user views the event list or clicks “Show Details”
Then the user should be able to see the cached event details


Scenario 2: Show an error when the user changes search settings (city, number of events). 
Given the device has no internet connection
When the user attempts to change the “City” or “Number of Events”
Then the app should display an error message
And the message should read “Search results cannot be found. Try again when there is an internet connection.”

```

```

Feature 5: Add an App Shortcut to the Home Screen 
Scenario 1: Users can install the meet app as a shortcut on their device home screen. 
Given the user is accessing the app via a mobile browser
When the user select the “Add to Home Screen” option
Then an app shortcut icon should be created on the device home screen
And the user should be able to launch the app directly from that icon

```

```
Feature 6: Display Charts Visualizing Event Details

Scenario 1: Show a chart with the number of upcoming events in each city.
Given the app is open
And several events are loaded for different cities
When the user clicks the  “Display Charts” button
Then a chart should be displayed visualizing the number of events in each city
And the chart should accurately reflect the data currently in the event list

```

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh
