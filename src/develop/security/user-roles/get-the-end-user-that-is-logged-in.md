---
tags: support-Security
---

# Get the End-User That Is Logged In

It is common to have applications that ask for end-user authentication to use
them. Besides restricting application access to authenticated end-users, it
also allows implementing user-specific logic. For example, display the
information on the home screen adapted to the end-user that is logged in.

To get the end-user currently logged in to the application, use the
GetUserId()  function.

##  Example

In the GoOut mobile application, for finding, reviewing and rating places, we
want to know the end-user who wrote a review. For that, we have to save the
end-user identifier in the review:

1. Go to the  AddReview  screen and open the Save action; 
2. Assign the value returned by  GetUserId()  to attribute  Review.UserId  ; 
3. Create the review using the  CreateReview  entity action.

