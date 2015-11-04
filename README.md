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
