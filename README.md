# Last battle before the holy finals

Now it's time to apply all learned concepts altogether.

Let's train train the main fullstack concepts once more in a mini project

- Fetching, display data from backend routes
- Updating data in the backend
- Signup & Login with Tokens & Cookies
- Password hashing
- Setting up relational data
- Creating & protect user specific data
- Validate incoming data to prevent messy stuff from going into the DB
- Deployment of frontend & backend
- If still time: Additional goodies from the workshops, like File Upload, Social Login or... some Chat feature! (see last stage below)

## Instructions

We wanna create an app where we can signup and create user specific content.

The concrete content you wanna manage is completely up to you as a team.

Possible things to manage:

- todos, recipes, notes, journal, contact list, etc...

Not logged-in users are just able to view the homepage.

A logged-in user should just be able to view his OWN content. But not to see content of other users.

All data fetched from the API, including the login status, should get stored centrally in Context API.

## :3rd_place_medal: BASIC Edition - Homepage, Auth and Content Area

Create these basic pages

- Homepage
- Signup & Login page(s)
- Protected user area page with contents

Backend: 
- Setup schemas for users and the content 
- Seed in some users with dummy contents
- Provide routes to signup & login
- Provide routes to fetch user specific content

### Integration 

Test the login & display of user specific contents in the Content Page

Protect the User Content page for logged in users only.

If a user tries to access the content page directly, without being logged in, please redirect the user to the Login page.


<br /><br />

## :2nd_place_medal: SILVER EDITION: Content CRUD & Logout

In this edition we wanna allow full CRUD on the contents.

All changes of an item in the API should also get updated in your context state.

Here you can see examples how to update your Frontend state after a operation (create, update, delete):
https://github.com/losrobbos/api-connect-guide#using-fetch

Just allow logged-in users to update data.

### Logout

Provide a logout link in your navbar to logout the User.

You can logout a user against the API, by calling a logout route, which clears the browser cookie.

```
app.get("/logout", (req, res, next) => {
  res.clearCookie("token")
  res.json({ message: "Logged you out successfully" })
})

```

<br /><br />

## :trophy:	PLATINUM EDITION: Messaging

Add some chatting between users!

Setup a page where logged in users can meet in a room and exchange messages.

Usually for chats so called "WebSockets" are used. But that is a bit more complicated.

Explore how you can exchange messages between users using so called "Server-Sent-Events" (SSE):

- SSE - how to listen for an event stream: https://www.voorhoede.nl/en/blog/real-time-communication-with-server-sent-events/
- Example with React: https://auth0.com/blog/developing-real-time-web-applications-with-server-sent-events/

Hint: You do not need to store the chat messages in the backend. You can just forward (=broadcast) incoming messages to all other participants.

Protect the chat page for logged-in users only.

If you still got time and wanna take it one step further:

- Store incoming chat entries in a collection, e.g. "Messages"
- Send users joining the chat the last 10 messages of the chat

## General instructions

- Split up the team and code backend & frontend part in parallel
- Please use SEPARATE repositories for backend & frontend code!
- Ideally: Create an GitHub organisation and add all your teachers to it as members / collaborators
- Please use branches for coding & pull requests for integrating a new feature into the main branch

## Resources

### Fetch & State Updates

Wondering how to perform these freaky fetch calls against the API from React for GET, POST, PATCH/PUT, DELETE? And what to do with the results to keep central data (API) and local data (state) in sync?

Checkout the API connect guide with Fetch examples: https://github.com/losrobbos/api-connect-guide#using-fetch

### Gitty gitty...

Wondering how to do Git Branching & Merging in a team? 

Checkout this mini guide on the GitHub Flow method with concrete GIT commands for your branching workflow: https://github.com/losrobbos/github-flow-guide/blob/main/GIT_WORKFLOW.github.md
