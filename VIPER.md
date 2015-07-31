
1.[VIPER](http://www.objc.io/issues/13-architecture/viper/)

2.[Introduction to VIPER](http://mutualmobile.github.io/blog/2013/12/04/viper-introduction/)

#VIPER

##Basics
What is VIPER? VIPER is a programming architecture which tries to improve the MVC architecture. The idea is that each project should be divided by five main layers of responsibily. 
 - View
 - Interactor
 - Presenter
 - Entity
 - Routing

By doing that, the project follows the [Single responsibility principle](https://en.wikipedia.org/wiki/Single_responsibility_principle).This makes testing easier, you can test each layer individuali. The functionality of the application should be divided by [Use cases](https://en.wikipedia.org/wiki/Use_case). Each layer should consist of a common class, from which there would be derived classes for each use case. The leyer should communicate via protocols. That modularity enables easy replacment of different segments.
 

##View

The View is passive. It waits for the Presenter to give it content to display; it never asks the Presenter for data. Methods defined for a View (e.g. LoginView for a login screen) should allow a Presenter to communicate at a higher level of abstraction, expressed in terms of its content, and not how that content is to be displayed. The view should only invoce the pressenter when the user inputs information. 
The view communicates with the presenter.

##Interactor

An Interactor represents a single use case in the app. It contains the business logic to manipulate model objects or Entities to carry out a specific task. The work done in an Interactor should be independent of any UI. The same Interactor could be used in an iOS app or an OS X app.
If there are many entities the interactor should acces them via a [Data store](https://en.wikipedia.org/wiki/Data_architecture).
The Interactor communicates with the Presenter and the Entities.

##Presenter

The Presenter's main function is to present the [UI](https://en.wikipedia.org/wiki/User_interface). It gathers from the user interaction, and forwards it to the interactor. It knows when to present the user interface. The presenter ask the WireFrame or Routing if there are any changes to the UI, he does not change the UI itself.

##Entity

The entity is pure data. The class in which we store it. If there is a need, there can be some simple methods which manipulate it. But it would be better that any major changes or complex work would be done in the interactor layer. The Entities role is to store data, not to handle it.

##Routing

##Conclusion
