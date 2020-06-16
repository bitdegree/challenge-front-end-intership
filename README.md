# Task for Front End Intership

## Few simple steps

1. Fork this repo
2. Create a simple comment box
3. Prepare pull request and let us know that you are done

## General guidelines

* Use common sense and don't spend too much time on a single task if you get stuck
* This task might not specify every single detail of how it should be implemented. When in doubt, improvise and go with a solution that you think would work best for a project like this.
* Optional tasks are not required for you to complete. But if you're going to do them, start with them as they require some extra initial set up.

## Requirements

* Comment box design is provided in `assets` folder
* Use Boostrap 4
* Use Vue.js as your framework

## Functional requirements

* It should be possible to add new comments using the input at the bottom (it's fine to use random names and avatars, but you can also create inputs for those fields)
* All data should be synced with browser's local storage. It means that the comments should persist even if the page is reloaded.
* By default the comment box should only display 4 latest comments. The number of hidden comments is written at the top of the container. If the user clicks on the that number, 20 more comments should show up. This action can be repeated until there are no more hidden comments. The number of hidden comments should update each time the button is clicked. The button should disappear completely once all comments are visible.
* There should be a link or a button that would allow the user to delete individual comments. Make sure the link is only visible when user hovers over the comment. Style the link / button in a way that would match the overall look & feel.
* Use transitions and / or animations where you think it's applicable.

## Optional tasks

* Add support for nested comments: the user should be able to respond to any comment or sub-comment. Design the reply button / text input the way you think it's better but make sure it matches the overall look & feel of the comment box.
* Depth of the nested comments should be limited and that limit should be easy to change if needed. For example, if you set the depth to `2` only replies to the main comments are possible but sub-comments cannot be replied to. Switching it to `3` would allow an extra layer of replies.
* All replies and sub-comments should be hidden by default. It should only say `View X replies` where `X` is the number of replies for a specific (sub)comment. Once clicked, the text should disappear and comments should show up.
* Like before, comments should be deletable and all data should be synced with local storage.

## Few tips
- We always prefer the code that is robust, easy to read and re-usable
- Make design user friendly
- Have fun!
