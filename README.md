# WishWeave: idea to build canvas

**Live demo:** [mamun-abdu.github.io/wishweave-showcase](https://mamun-abdu.github.io/wishweave-showcase/)

WishWeave is a small browser app that turns a rough idea into a short build canvas and shows related ideas next to it. It came from a problem I ran into on a community wishlist: an idea can look new simply because similar ones are hard to find.

It is one HTML file. No account, no build step, no external API.

## What it does

- You write a rough idea, with an optional title. It doesn't need to be polished.
- It fills in a build canvas: the problem, who it helps, a possible solution, and a next small step.
- It pulls a few tags out of your text.
- It compares your idea with a small built-in library of example ideas and shows the three closest, with a percentage overlap.
- You can copy the canvas as plain text or save up to six drafts in your browser (`localStorage`).

## How the matching works

On purpose, it's simple and easy to check. It is not an AI search engine.

1. The text is lowercased and split into words. Short words and common filler words are dropped.
2. Overlap with each example idea is the number of shared words divided by the number of distinct words in both (Jaccard similarity), shown as a percentage.
3. The "who it helps" and "next step" lines come from a few keyword rules (for example, words like `aws` or `cloud` point to cloud builders).
4. The meter at the top of the canvas only reflects how many distinct keywords you wrote. It is not a quality score.

## Run it locally

Download or clone the repo and open `index.html` in any modern browser.

```bash
git clone https://github.com/mamun-abdu/wishweave-showcase.git
cd wishweave-showcase
```

Then double-click `index.html`, or serve the folder with `python3 -m http.server` and visit `http://localhost:8000`.

## Hosting

The live demo runs on GitHub Pages. Because it's a single static file, any static host works too. The original challenge write-up described hosting it on AWS Amplify Hosting:

1. In the AWS Amplify console, choose **New app → Host web app → GitHub**.
2. Authorize the AWS Amplify GitHub App and pick this repository.
3. Keep the default static-site settings and choose **Save and deploy**.

## Background

The concept started as my AWS Builder Center wishlist idea, "Show Related Wishes Before I Post." This showcase turns that wish into a working prototype for the Weekend Showcase Challenge.

This is an independent community project. It is not an AWS product.

## License

MIT. See [LICENSE](LICENSE).
