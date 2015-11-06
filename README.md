# ionic-example
follow the course on Udemy: Rapid prototyping with Ionic

Section 8: Style the Stock View

Resources
CSS Selector: http://www.w3schools.com/cssref/css_selectors.asp

CSS Cascading: http://www.w3.org/TR/CSS21/cascade.html

CSS Specificity: https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity

Summary

In this section, we styled the stock view template in style.css. We use id's and classes, which we added to the view template, to select the elements we style. In order to locate the required selectors for the chart, we used Chrome's Dev Tools dock to navigate through the DOM tree and test styling some components.

We approached styling the view by considering the most important information and how to make those data jump out, so the user can take in that information with little effort. We also added drag-content directives to the view, so pulling the context chart won't drag the window.
We made the view's navbar's color reactive by adding an ngStyle class, which adds the value of an expression from the controller. We set the value of that expression by evaluating the returned price data.
We used classes from Ionic's grid system to format the market data card's columns. Lastly, we added the last trade time to the market data card's header.

Section 9: Angular Cache

Install cache under www folder: looks like "bower install --save angular-cache" not working for me, so I download zip file from
http://jmdobry.github.io/angular-cache/ and manually put into www/lib folder.

Section 11: Add News Feed

XML to JSON library: https://code.google.com/p/x2js/

Yahoo RSS News Feed: https://code.google.com/p/yahoo-finance-managed/wiki/miscapiRssFeed

Summary

In this section, we install a third party JavaScript library that converts XML data to JSON, then configure a service that retrieves data from RSS feeds via another Yahoo API. We do not, however, install or configure the inAppBrowser plugin.

Then we style the news card in style.css.

Lastly, we implement a new filter that limits the number of characters in a component in the view.

Section 12: Add Follow and Unfollow Stocks Functionality

Summary

In this section, we add the follow and unfollow stocks functionality.

We implement a service to cache the my stocks array, as well as set the default stocks when the app first launches on a device.

We load the cached array of default stocks into the view by setting the myStocksArray scope expression to an array returned by the myStocksArrayService.

In order to check if a certain stock is being followed, we use a for loop to check the passed in stock against the my stocks array. We use the result of this expression in the view to determine the (un)follow button's contents.

Section 13: Add Stock Searching Functionality

Summary

In this section, we add stock searching functionality.

We create a modal service, data service, controller, and view template for the search modal. We use an input component in the view to initialize a search function every time the input changes, passing in the input. We implement the search service method with the http service, but we use a custom callback, which we define through variables and a function.

We use Ionic's debounce feature to delay the initialization of the search method each time the modal's input changes.

We use the state service's go method to navigate to a stock's page from search results, passing in the stock's ticker as a state parameter.

Also, we call the close modal service method directly from the modal by defining a scope variable in the AppCtrl set to call the modalService.

Lastly, we style the modal in style.css and add an Ionic loading animation to the view to show when the search results are loading, in addition to a component that displays when there are no results for a given query, using ng-if, ng-hide, and ng-show directives.


Section 14: Build Out the My Stocks State

Summary

In this section, we build out the My Stocks view template and controller.

Firstly, we add another factory service for stock price data, as well as implement the caching of the price data in the getPriceData method.

We build an array with the stocks and their data in the controller by iterating over the my stocks array, each iteration calling the getPriceData method on that stock, and then pushing the information into the scope array. Also, we order the ng-repeat list using the orderBy filter.

We add option buttons to the My Stocks view list, which call the unfollow method.

We add pull to refresh functionality using an ion-refresher component.


Section 15: Firebase Integration — User Authentication

Summary

In this section, we finish implementing the modal service and build out the Log In and Sign Up modal view templates.

After, we add the LoginSignupCtrl.

Next, we install Firebase and then start building out the userService, which utilizes our Firebase factory and content services to call Firebase user authentication convenience methods. Then we test the service methods through the modals by signing up, logging in, and logging out a new user.

Lastly, we added logic to the Log In, Sign Up, and Log Out buttons in the side menu, so they will show and hide depending on whether a user is currently logged in.

Section 16: Firebase Integration — Read and Write Data to a Firebase Database

Summary

In this section, we continue integrating Firebase to finish implementing the userService. In order to sync a new user's notes and stocks when they sign up, we call Firebase's push and set methods in the log in service method.

Then, we add new service methods to update a logged in user's notes and stocks list when they make changes in the app.
We structure the data in the database in a users node, which has child nodes for each user, and in each user's node, we have stocks and notes nodes where that user's data is stored.
