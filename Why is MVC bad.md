1.[MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)

# Why is MVC bad in iOS

## Introduction
MVC or Model View Controller is an architecture concept which consist of three parts. As the name sugest , it consists of the Model, the View and the Controller. Regarding the basic MVC concept , you can read in the link that is provided at the top of this article.

## The problem

The apps are getting bigger and bigger. And with that there is more code. If you ever developed an app you know that the easiest way is to put the main part in the controller. Well it is the controller's job to control, and there is nothing wrong with the concept in that regard. But when you develop for applications for mobile phones, especially iOS, you don't have too much code in the view. You can do the whole view with the storyboard. The model is used just to store the data, which is again not a real problem. So, if you follow the concept, the controller has to do all the rest. And, that is the biggest problem, the controllers will get huge, and very hard to maintain. They don't follow the [Single responsibility principle](https://en.wikipedia.org/wiki/Single_responsibility_principle).
The next problem is that the Controller stores data, and by that he becomes a data source.
Further there is much duplicate code from one controller to another, which is bad.

## Solution

Well the solution is simple, do not use MVC. Well it is better to say don't use pure MVC, you could use MVC, but not in the standard form. So what are alternatives do you have? There are a couple of solutions which could help you to have a more structured app. 


## [MVVC](https://en.wikipedia.org/wiki/Model_View_ViewModel)

MVVC or Model View ViewModel is an architecture which is used by Microsoft and is a derivation from the standard MVC architecture. The model and the view are more or less the same as in the MVC paradigm. The difference is in the controller, which is an ViewModel and an Binder.

  - The View Model is an abstractation of the view, which exposes public properties to the binder.
  - The binder functionas as a mediate beetween the view and the view model

## Lightweight ViewControllers

The main concept is to split the ViewControllers in small parts. You have to do the following:

  - Separet Out Data Source and Other Protocols
  - Create a Store Class
  - Move the Web Service Logic to the Model Layer
  - Move View Code into the View Layer
  - Separate Communication
  
A more detail aproach can be found [here](http://www.objc.io/issues/1-view-controllers/lighter-view-controllers/#communication).

## Viper - our approach

The approach we chose is VIPER. The architecture consist of five elements
  - View
  - Interactor
  - Presenter
  - Entity
  - Routing
  
We will be discussing VIPER more in the next article. A good link about VIPER can be found [here](http://www.objc.io/issues/13-architecture/viper/).


