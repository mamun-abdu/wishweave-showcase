# WishWeave — Idea to Build Canvas

WishWeave is a small, browser-based creative app inspired by a simple problem I ran into while using a community wishlist: a good idea can look new simply because related ideas are hard to find.

## What it does

- Lets a builder write a rough idea without polishing it first.
- Turns the idea into a small build canvas: problem, audience, possible solution, and next step.
- Generates lightweight tags from the text.
- Compares the idea with a small demo library and surfaces related concepts.
- Saves drafts locally in the browser.
- Requires no account and no external API.

The matching is intentionally simple and transparent. It is not pretending to be an AI search engine; the point is to make the workflow useful first.

## AWS deployment

This project is a static web app and can be hosted with **AWS Amplify Hosting**.

1. Put `index.html` in a public GitHub repository.
2. Open the AWS Amplify console.
3. Choose **New app → Host web app → GitHub**.
4. Authorize the AWS Amplify GitHub App and select this repository.
5. Keep the default build settings for a static site if Amplify presents them, then choose **Save and deploy**.
6. Open the generated `amplifyapp.com` URL and test the app.

## Architecture

User → WishWeave static web app → browser localStorage

AWS layer:

GitHub repository → AWS Amplify Hosting → deployed HTTPS web app

The app deliberately keeps the prototype small. Amplify Hosting is the AWS service used for deployment and delivery.

## Challenge connection

The concept is inspired by my AWS Builder Center Wishlist idea, "Show Related Wishes Before I Post." The showcase version turns that idea into a working interactive prototype instead of leaving it as a wish.

## Local run

No build step is required. Open `index.html` in a browser.

## Notes

This is an independent community project and is not an AWS product.
