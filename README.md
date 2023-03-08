# Studying react:

## High-level look or Core aspects:

1. Components

Encapsulated units of functionality that are the fundamental unit of React. They consist of 
- functions
- classes
which maintain the internal state with all the received data. 

2. React libraries

They consist of React libraries,
- react (core react library)
- react-dom (handles rendering in browser or server-side environment)
- react-native (provides react native for iOS or Android)

3. 3rd party libraries

Ways to integrate non-react code with react code.

4. Running a react application

You can run on platform of your choice:
- web
- mobile
- native

#### React does not provide a complete solution for all aspects of app development; instead, it allows developers to choose the libraries for their preferred tasks

## Introducing react components

Lets assume we are exploring ReactJS as a possible technology for building a fictional startup called Letters. The provided mockup hints at the ability to post, comment & like. For this we must create components to get a feel of the technology.


### Understanding the application data

To understand the application data, we must first realize the information provided by the API. This is a key steps to understand shape of application data.


Lets take a look at a sample API:

~~~
{
  "id": 123,                                              
  "content": "What we hope ever to do with ease, we must first learn to do
     with diligence. — Samuel Johnson",
  "user": {
     "name": "Mark Thomas",
     "id": 1
  },
  "comments": [{                                          
    "id": 0,                                              
    "user": "David",
    "content": "too. mainstream."
  }, {
    "id": 1,
    "user": "Peter",
    "content": "Who was Samuel Johnson?"
  }, {
    "id": 2,
    "user": "Mitchell",
    "content": "@Peter get off Letters and do your homework!"
  }, {
    "id": 3,
    "user": "Peter",
    "content": "@mitchell ok dad :P"
  }]
}
~~~~

From the above sample we can extrapolate the following,
- This sample data is the JSON-formatted response of a single post 
- Sample data also consists a collection of comments
- All of the comments contain ids, authors and contents

Now we can use the above data to build components. We must also realize that React components are arranged in a tree-like structure, exactly like DOM elements. React components can be nested, appear "next to" other components at the same level. Due to this flexible nature of the components they are said to composable. 

Components are analogous to LEGO bricks. Each brick is self-contained and can be moved around easily. Due to which relations can be formed using components: parent and child type. If a component contains another component, it's said to be the parent. A component within another component is said to be the child. Any components which are the same level don't care about other components, they are only "care" about their parents and children.

Types of component:
- Standalone component
- Composite component 
    * parent - child

Remember the following while creating components:
- Ensure logical grouping of components
- Repeating interface elements are candidates for being component
- Iterating & improving your code is essential

In our use case, we have the following components
- comment-box component 
- post-comment component
- comment-section component
- create-comment component

here, comment-box component contains post-comment, comment-section and create-comment component, this is a parent-child relation with multiple children belonging to a single parent.


### Beginning to code

To begin with the code, we have relied on https://codesandbox.io/ to help with a starter project. We would be working three libraries react, react-dom & prop-types.

react - core library for react
react-dom - handles rendering components to DOM
prop-types - helps perform typechecking on some components

Now, we start with creating the comment box component by creating some of the constituent parts first.A
