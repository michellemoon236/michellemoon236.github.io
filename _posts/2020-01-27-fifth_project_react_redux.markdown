---
layout: post
title:      "Fifth Project: React Redux"
date:       2020-01-27 23:37:05 +0000
permalink:  fifth_project_react_redux
---


My last project is single webpage application called Book Tally that lets the user keep track of books they would like to read. The website combines a React Redux frontend and Rails API backend. This final project was a culmination of several languages we learned and helped me see how frontend and backend work together. 

Incorporating Redux into a React application was a great solution for allowing a larger application with many container/component elements to all have access to the same data (state) stored as a Javascript object called store. Any component that was simply connected to the store therefore had access to the application’s global state. I could then use the mapStateToProps function to map the specific part of the global state I wanted to access to the props for that specific component so it was accessible to use and update through that component’s props. 

With this project I was also able to include Thunk middleware which enabled me to get data from an external source, i.e. API, using fetch web requests. Since web requests in Javascript are asynchronous, Thunk is needed for the data to be fetched correctly. Thunk does this by calling a second dispatch action to update the state with the data only after the promise from the fetch is resolved.

