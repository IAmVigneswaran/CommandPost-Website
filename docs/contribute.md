# Contribute

The CommandPost website is entirely open source and hosted on [GitHub](https://github.com).

[GitHub](https://github.com) is a **safe and secure** developers platform used by **over 73 million users** worldwide.

CommandPost uses [VentraIP](https://ventraip.com.au) for domain hosting.

You can make changes to the site by [submitting pull requests on GitHub](https://github.com/CommandPost/CommandPost-Website).

We welcome and encourage users submitting changes to the website's content.

You can see all the current contributors [here](https://github.com/CommandPost/CommandPost-Website/graphs/contributors). Everything is tracked and archived on [GitHub](https://github.com/CommandPost/CommandPost-Website).

The entire site is written in [Markdown](https://www.markdownguide.org), so it's very easy to modify and update without necessarily knowing any HTML or code.

The website is build on [Retype](https://retype.com), which has a lot of power and flexibility, so you can easily add all kinds of [components](https://retype.com/components/) just using Markdown.

However, if you're not confident using GitHub, you can also email us content here: [support@latenitefilms.com](mailto:support@latenitefilms.com?subject=FCPCafe)

---

### Our To-Do List

If you're interested in collaborating, and helping the CommandPost website grow, here's some ideas of some of the things you can do:

- Add any missing documentation
- Replace still images with GIFs

---

### Our Mission

We want this site to be:

- **Open:** This site will remain open-source on GitHub for anyone to suggest pull requests
- **Up-to-date & Relevant:** We want this site to always be up-to-date and relevant
- **No bullshit:** We want this site to be honest, truthful, useful and professional
- **Community Driven:** This isn't our site, it's "owned" by the professional CommandPost Community
- **Modern:** This site should work great on the latest browsers, including mobile
- **Fast & Clean:** This site should load quickly, and be easy to navigate
- **No analytics or user tracking:** No cookies here!

---

### What's a Pull Request?

Imagine you're working with a group of friends on a big school project, and you're all adding different parts to it. Now, you're all using the same master copy of the project, but you're all working separately. When you're ready to add your part to the master copy, you don't just want to plop it in there. You want your friends to check it over, make sure it fits with everything else, and then add it in when they agree it's ready. This way, you ensure that everyone's work meshes well together and the project doesn't become a mess.

A GitHub pull request is basically the same idea. When you're working on a shared codebase, or "project," you often work on your own copy, or "branch". When you think your changes are ready to be added to the shared codebase, you make a "pull request". This is a proposal that says "I think these changes I made should be added to our shared project".

Your teammates then can look over your changes, suggest edits, and finally, if they agree that your changes are good, they "merge" them into the shared project. This way, everyone keeps the code clean and organized, and you have a record of who added what and when.

So, in simple terms, **a pull request is a way of proposing changes to a shared project** and allowing others to review and approve those changes before they're added.

---

### Navigating GitHub

To create the fastest website possible, CommandPost is what's called a "static site". It just a collection of HTML files in a folder - nothing fancy.

However, to make sure the website is super easy to update and improve, we use [GitHub Actions](https://github.com/features/actions) to "do stuff" to our markdown files whenever we submit a pull request.

For example, each time you make a pull request, our [fancy GitHub Action](https://github.com/CommandPost/CommandPost-Website/blob/main/.github/workflows/retype-action.yml) does the following:

- Pulls all the latest [GitHub issues](https://github.com/CommandPost/CommandPost/issues) and populates the [Wish List](/wish-list/) and [Bug Tracker](/bugtracker/) pages.
- Update the [Sponsor](/sponsor/) page with latest GitHub Sponsors.
- Looks at all the individual **Snippets** in [this folder](https://github.com/CommandPost/CommandPost-Website/tree/main/docs/_includes/snippets), and generates an alphabetical list of them for the [Snippets Library page](/scripting/snippets-library/).

This means, if you want to add a Snippet to the [Snippets Library](/scripting/snippets-library/), you can just add a new markdown file in that folder, and once the pull request is approved, everything will be updated automagically.

---

### How to Edit Pages

If you're not already registered with GitHub, [create a free account](https://github.com/join).

There's an **Edit this page on GitHub** link at the bottom of every page.

![Edit this file](../static/editthispage.png)

You can edit the contents of this page by clicking the link at the bottom of this page.

To make changes simply click the little pencil **Edit this file** button.

![Edit this file](../static/editthisfile.png)

You can then make changes in the text editor using the Markdown syntax. Copying and pasting existing syntax is the best way to get started.

You should make sure all external links open in a new tab/window (edit this page to see how that works).

You can learn more about basic formatting [here](https://retype.com/guides/formatting/).

![Edit this file](../static/editor.png)

Once done click **Commit changes**. You can enter a message and description for the commit. Press **Commit changes** again.

![Edit this file](../static/proposechanges.png)

You will now be presented with a **Open a pull request** page.

You can add a title and detailed description to the pull request. Once you're done click **Create pull request**.

![Edit this file](../static/pullrequest.png)

This will send your changes to the CommandPost team to review and approve.

If changes are required, they'll add comments within the pull request.

If you have questions, you can ask them on the [Discussions board](https://github.com/CommandPost/CommandPost/discussions).

You can also email us here: [support@latenitefilms.com](mailto:support@latenitefilms.com?subject=CommandPost)

---

### GitHub Web-based Editor

You can use the [github.dev](https://github.dev) web-based editor to edit files and commit your changes.

Simply replace the `.com` with `.dev` on any GitHub URL.

For example to edit this page you can use:

```
https://github.dev/CommandPost/CommandPost-Website/blob/main/docs/contribute.md
```

You can learn more [here](https://docs.github.com/en/codespaces/the-githubdev-web-based-editor).

---

### External Links

All external links should open in a new tab/window.

The trick is to add `` at the end of the link.

Here's an example of how to do this in Markdown:

```
[Sync-N-Link](/tools/#sync-n-link-x)
```

---

### Embedded Videos

To keep that site as fast as possible, and free from tracking/cookies, we've decided **not** to allow embedded videos.

Instead, we'll be posting the Video Thumbnail as a clickable link to the video.

Here's an example of how this looks in Markdown:

```
[![](/static/caption-converter.jpg)](https://www.youtube.com/watch?v=2VOY70LfA-4)
```

You can use [this website](https://youtube-thumbnail-grabber.com) for download YouTube Thumbnails.

---

### Images

All images should be stored within the `/docs/static/` folder on GitHub.

You can find it [here](https://github.com/CommandPost/CommandPost-Website/tree/main/docs/static).

---

### GitHub Desktop

You can also use GitHub Desktop to essentially "clone" the entire CommandPost website to your local machine.

You can then make changes locally, and once done, submit a pull request back to the main GitHub repository.

You can download GitHub Desktop [here](https://desktop.github.com).

You can then use a text editor like [BBEdit](https://www.barebones.com/products/bbedit/) to edit your Markdown files on your Mac.

---

### Powered by Retype

The CommandPost Website is powered by [Retype](https://retype.com) and hosted on [GitHub Pages](https://pages.github.com).

We've VERY thankful for [all the support](https://github.com/retypeapp/retype/issues/created_by/latenitefilms) Retype has given us!

The comments feature at the bottom of every page is powered by [giscus](https://giscus.vercel.app).

---

### Contributor Covenant Code of Conduct

#### Our Pledge

We as members, contributors, and leaders pledge to make participation in our
community a harassment-free experience for everyone, regardless of age, body
size, visible or invisible disability, ethnicity, sex characteristics, gender
identity and expression, level of experience, education, socio-economic status,
nationality, personal appearance, race, caste, color, religion, or sexual
identity and orientation.

We pledge to act and interact in ways that contribute to an open, welcoming,
diverse, inclusive, and healthy community.

#### Our Standards

Examples of behavior that contributes to a positive environment for our
community include:

* Demonstrating empathy and kindness toward other people
* Being respectful of differing opinions, viewpoints, and experiences
* Giving and gracefully accepting constructive feedback
* Accepting responsibility and apologizing to those affected by our mistakes,
  and learning from the experience
* Focusing on what is best not just for us as individuals, but for the overall
  community

Examples of unacceptable behavior include:

* The use of sexualized language or imagery, and sexual attention or advances of
  any kind
* Trolling, insulting or derogatory comments, and personal or political attacks
* Public or private harassment
* Publishing others' private information, such as a physical or email address,
  without their explicit permission
* Other conduct which could reasonably be considered inappropriate in a
  professional setting

#### Enforcement Responsibilities

Community leaders are responsible for clarifying and enforcing our standards of
acceptable behavior and will take appropriate and fair corrective action in
response to any behavior that they deem inappropriate, threatening, offensive,
or harmful.

Community leaders have the right and responsibility to remove, edit, or reject
comments, commits, code, wiki edits, issues, and other contributions that are
not aligned to this Code of Conduct, and will communicate reasons for moderation
decisions when appropriate.

#### Scope

This Code of Conduct applies within all community spaces, and also applies when
an individual is officially representing the community in public spaces.
Examples of representing our community include using an official e-mail address,
posting via an official social media account, or acting as an appointed
representative at an online or offline event.

#### Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be
reported to the community leaders responsible for enforcement at
[INSERT CONTACT METHOD].
All complaints will be reviewed and investigated promptly and fairly.

All community leaders are obligated to respect the privacy and security of the
reporter of any incident.

#### Enforcement Guidelines

Community leaders will follow these Community Impact Guidelines in determining
the consequences for any action they deem in violation of this Code of Conduct:

##### 1. Correction

**Community Impact**: Use of inappropriate language or other behavior deemed
unprofessional or unwelcome in the community.

**Consequence**: A private, written warning from community leaders, providing
clarity around the nature of the violation and an explanation of why the
behavior was inappropriate. A public apology may be requested.

##### 2. Warning

**Community Impact**: A violation through a single incident or series of
actions.

**Consequence**: A warning with consequences for continued behavior. No
interaction with the people involved, including unsolicited interaction with
those enforcing the Code of Conduct, for a specified period of time. This
includes avoiding interactions in community spaces as well as external channels
like social media. Violating these terms may lead to a temporary or permanent
ban.

##### 3. Temporary Ban

**Community Impact**: A serious violation of community standards, including
sustained inappropriate behavior.

**Consequence**: A temporary ban from any sort of interaction or public
communication with the community for a specified period of time. No public or
private interaction with the people involved, including unsolicited interaction
with those enforcing the Code of Conduct, is allowed during this period.
Violating these terms may lead to a permanent ban.

##### 4. Permanent Ban

**Community Impact**: Demonstrating a pattern of violation of community
standards, including sustained inappropriate behavior, harassment of an
individual, or aggression toward or disparagement of classes of individuals.

**Consequence**: A permanent ban from any sort of public interaction within the
community.

#### Attribution

This Code of Conduct is adapted from the [Contributor Covenant][homepage],
version 2.1, available at
[https://www.contributor-covenant.org/version/2/1/code_of_conduct.html][v2.1].

Community Impact Guidelines were inspired by
[Mozilla's code of conduct enforcement ladder][Mozilla CoC].

For answers to common questions about this code of conduct, see the FAQ at
[https://www.contributor-covenant.org/faq][FAQ]. Translations are available at
[https://www.contributor-covenant.org/translations][translations].

[homepage]: https://www.contributor-covenant.org
[v2.1]: https://www.contributor-covenant.org/version/2/1/code_of_conduct.html
[Mozilla CoC]: https://github.com/mozilla/diversity
[FAQ]: https://www.contributor-covenant.org/faq
[translations]: https://www.contributor-covenant.org/translations
