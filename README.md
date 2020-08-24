# Sendle front end developer take home exercise

**DO NOT FORK THIS REPOSITORY IN GITHUB, CLONE IT AND FOLLOW THE INSTRUCTIONS FOR SUBMISSION AT THE END OF THE README**

Hi, thanks for completing the front end developer take home exercise

The purpose of this exercise is for us to get a sense of your skill level with CSS,
JavaScript, and React and to see how you think and your approach to solving problems.

The problem we've chosen is a quoting tool, similar to what exists on
in Sendle. This will involve working with Sendle's quoting API to fetch
data from the pricing system, as well as handling and responding to
errors and building a small user interface.

* Write as many additional tests and classes as you feel you need.
* It's up to you to define the data structures used
* Feel free to use any additional packages you think will help. Of course, the goal here is to show us clean, readable code and allow
  us to see that you have maintainability and correctness at the forefront of your thinking, so keep
  that in mind.

Good luck, have fun.

## The Brief

### Single Page Quote Tool

This project is a small quote tool designed to help users get instant shipping quotes on the go. It uses the Sendle API to return rates and delivery ETAs based on the pickup and delivery information that is input by the user. The rates are filtered by plan.

### How it works

The tool consists of a form, where the user enters pickup and delivery location details, and a results screen that shows shipping rates for each of Sendle's parcel sizes, and a delivery ETA for that route when the "get quote" button is clicked.

The input route is shown at the top of the results screen and clicking "change route" will take the user back to the form so they can enter new details and resubmit.

Using a select dropdown at the top of the rates table, the user can choose one of three Sendle plans to view different prices.

"Start sendling now" takes the user to the sign-in screen at [https://www.sendle.com/users/sign_in](https://www.sendle.com/users/sign_in)

### Design files

Project designs can be viewed, downloaded and/or inspected via Sketch Cloud here - [https://www.sketch.com/s/6d161d05-ba5d-430c-a601-bb0cf35a9433](https://www.sketch.com/s/6d161d05-ba5d-430c-a601-bb0cf35a9433)

### A bit about plans

Sendle's Standard plan is "perfect for personal senders" and has no minimum parcel orders.

Premium is "designed for small business" and requires a minimum of 20 parcel orders per month.

Pro is "ideal for established business" and requires a minimum of 200 parcel orders per month.

### Technical Notes

Documentation for Sendle's API can be found here: [https://api-doc.sendle.com/#getting-quotes](https://api-doc.sendle.com/#getting-quotes)

Invalid quote requests will return a JSON error payload from the server with a 422 response, for example: 

```json
{
	"messages": {
		"pickup_suburb":["does not match Pickup Postcode"],
		"pickup_postcode":["does not match Pickup Suburb"]
	},
	"error": "unprocessable_entity",
  "error_description": "The data you supplied is invalid. Error messages are in the messages section. Please fix those fields and try again."
}
```


## Getting Started

This application has been bootstrapped with [create-react-app](https://create-react-app.dev/docs/getting-started/). We use [yarn](https://yarnpkg.com/), but this should work with npm if that's your preference.

```
yarn start
yarn run test
```

## FAQ

### Do I need an account to get quotes?

No, the quoting API supports [unauthenticated access](https://api-doc.sendle.com/#getting-quotes) which will return price points for all plans for the requested route and parcel size.

### Can I get all price points in one request via the API?

No, you will need to query the API for each size and route combination. Size break points are on [screen 3](https://www.sketch.com/s/6d161d05-ba5d-430c-a601-bb0cf35a9433/a/jmqwkG) in Sketch. The quoting API does not require volume to be provided.

## Submitting your work

When you have completed the exercise and wish to submit your work, please do the following:

1. Make sure all your work is commited to your branch, good commit messages and telling a story
   through the commits is a good thing.
2. Zip up the folder containing your repo and send to either your recruitment contact or jobs@sendle.com.

**DO NOT PUSH THE REPO UP TO GITHUB OR CREATE A PULL REQUEST AGAINST THIS REPO.**
