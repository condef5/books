# TK Restaurants

A test project for [Tekton Labs](https://www.tektonlabs.com) to evaluate the skill level, solutions mindedness, and responsiveness of RoR developers.

## Status

- **Completion Level:** [Fill with your current status]

# Getting started

[ Fill with your guide ]

---

# Back Story

We have moved to a new office. Our last office was located near Kennedy Park and there were plenty of restaurants to go. Now, we are located in Juan de Aliaga's WeWork, in Magdalenta. At first, we didn't know where to go for lunch.

After a while, we started discovering some good spots to have a great meal. However, we are 50+ people, some people discovered some places that others weren't aware of.

# Your Mission

We want you to build a simple web app that shows in a map the 10 nearest restaurants of a given location. The users can CRUD locations. The user could also select one of those restaurants, view its details and mark it as favorite.

The restaurants will be showed using the data provided by Foursquare API. The map and pins will be provided by Google Maps API.

## Requirements

1. Provide a view that shows a map. If there's a location selected, it will show the location on the map, along with multiple pin icons for the near restaurants. If no location is selected, prompt the user to pick a location from the list or create one.

1. To get the info of the restaurants, use the [foursquare2 gem](https://github.com/mattmueller/foursquare2) (Venues section).

1. When you click on a restaurant pin icon, the app must show a modal with some details of the restaurant. Use the gem again to fetch more details about that specific restaurant.

1. Display a favorite icon/button on the restaurant modal that allows to mark that place as favorite.

1. Provide a CRUD UI for the user locations. Feel free to use the attributes that you consider neccesary to fulfill the next requirements.

1. Provide a view that list your favorite restaurants and lets you remove them if you decide so. For each restaurant, remember to show the location associated to it.

## Additional considerations

- We want to test your RoR skills so *it is compulsory to use Rails for the backend*.
- Feel free to use any other framework for the front like React, Vue, Angular or just Rails
- Have a detailed explanation of setup / usage in this README. Fill the gap in **Getting Started**.
- Provide a `DETAILS.md` file with your process of solving these problems, snags you hit, things you learned, etc along with the number of hours required to finish the task.
- **Do NOT commit to master.** Create a branch with your full name as the name of the branch and commit only to that.
- Create a pull request from your branch to master branch.
- If you have any questions or want to say something, feel free to create a Github Issue or comment a line of code inside your PR. Remember to tag us in order to be notified of that.

## Bonus Points

- Support multiple users on the app. That means you need to provide an extra view for the login/signup and that a user can't access the map, locations, favorites view without authentication.
- Users must have their own locations and favorite restaurants. However, if a user picks a favorite that other user has already, it will be shown somewhere in the UI.
- Show a ranking of the favorite restaurants among all the users.

## Bonus Bonus Points

- Avoid reloading the page for every request and prefer using AJAX requests.
- Add some tests. Either for backend, frontend or both. The more the better.
