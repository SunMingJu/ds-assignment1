## Serverless REST Assignment.

__Name:__ MingJu Sun

__Video demonstration:__ https://youtu.be/-7rEICh9D0s

This repository contains an implementation of a serverless REST API for the AWS platform. The CDK framework is used to provision its infrastructure. The API's domain context is movie reviews.

### API endpoints.

__App API:__
+ POST /movies/reviews - add a movie review. **[Requires Authentication]**
+ GET /movies/{movieId}/reviews - Get all the reviews for the specified movie.
+ GET /movies/{movieId}/reviews?minRating=n - Get the reviews for the specified movie with a rating greater than the minRating.
+ GET /movies/{movieId}/reviews/{reviewerName} - Get the review written by the named reviewer for the specified movie.
+ PUT /movies/{movieId}/reviews/{reviewerName} - Update the text of a review. **[Requires Authentication]**
+ GET /movies/{movieId}/reviews/{year} - Get the reviews written in a specific year for a specific movie.
+ GET /reviews/{reviewerName} - Get all the reviews written by a specific reviewer.
+ GET /reviews/{reviewerName}/{movieId}/translation?language=code - Get a translated version of a movie review using the movie ID and reviewer name as the identifier.

![](./images/001.png)

__Auth API:__

+ POST /auth/signup - Register for an account.
+ POST /auth/confirm_signup - Confirm account registration with confirmation code.
+ POST /auth/signin - Sign into an account/authenticate.
+ GET /auth/signout - Sign out of an account/deauthenticate.

![](./images/002.png)

### Authentication.

![](./images/003.png)

### Independent learning (If relevant).

+ Functionality: Review translations:
    + Files of evidence:
        + lambda/translateReview.ts

+ Infrastructure: Lamdbd layers or Multi-stack app:
    + Files of evidence:
        + lib/app-api.ts
        + lib/auth-api.ts
        + lib/ds-assignment1-stack.ts        