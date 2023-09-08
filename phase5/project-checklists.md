---
layout: topic
title: Project Checklists
topic: Agile
category: phase4
parent: Phase 4
nav_order: 5
published: true
---

## 🏃‍♀️ Your First Sprint

We're just about ready to dive into the code.

Today you should be finalizing planning and doing research on data, technology, and tools you might need. If you are learning something new to build this project, this weekend is a great time to do a short tutorial to get up to speed.

Daily standup and project check-ins start on Monday!

📆 You'll have calendar invitations for your team's standup and check-in times. [The detailed schedule for next week and on is also posted here on the course site]({% link phase4/detailed-schedule.md %}).

Skim the following checklists to make sure you're ready.

### ✅ Checklist for the whole team, before you write code

- MVP is clearly defined and you know _exactly_ what you are building.
- You've discussed implementation and know at a high-level _how_ you are building this product.
- User stories and tasks (at minimum, for MVP) have been added to your Trello board _User Stories_ and _Backlog_ lists.
- First tasks are queued in _Current Sprint_.
- You have [created a team organization on GitHub](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/creating-a-new-organization-from-scratch) and added every team member.
- You have created your project repo or repos on GitHub and made sure everyone is added as a collaborator.
    - A `.gitignore` file is in your repo. You can get one that is specific to your project at [gitignore.io](https://www.toptal.com/developers/gitignore). Even more handy: use this [VS Code extension](https://marketplace.visualstudio.com/items?itemName=codezombiech.gitignore).
    - **Pin GitHub links at the top of your Slack channel**.
- Your team is clear on the Git and GitHub workflow and process for reviewing and merging pull requests.
- **Consider appointing a team lead** who can be responsible for running meetings, leading at check-in, and looking after the Trello board. Even better: rotate this role to share the responsibility.

### ✅ Back-end Getting Started Checklist

- **Models!** How will you represent the _nouns_ your project needs?
    - What fields belong on those models? Use the [Django Model Field Reference](https://docs.djangoproject.com/en/4.0/ref/models/fields/).
    - What relationships exist between the models? (one-to-many, many-to-many?)
        - Consider using [the CRC model](http://agilemodeling.com/artifacts/crcModel.htm) to help guide your discussions.
        - You should create an ER (entity relationship) diagram for your models to map relationships. This may change as you work, but you should have thought through and documented your plan to start with.
- What data will the front-end need from the back-end?
- What endpoints will you need to deliver that data?
    - Are you returning HTML? What templates does the front end need, and who will make those?
    - Are you returning JSON? How will you structure your data?
- 🚨 Make sure you are using `django-environ` (or something similar) and a `.env` file. This will be especially important for secret keys and sensitive info, like AWS credentials. **DON'T COMMIT YOUR SECRET KEYS!**
- Make sure you are using Postgres and not SQLite.
- Make a custom user model before you migrate.
- Write documentation early and make sure your front end has access to it.
- Deploy early.
    - Make sure more than one person on your team has access to the account/dashboard on your deployment service.
    - Plan to keep an eye on your production app.
    - Every time you merge a pull request and the main branch changes, it will trigger a new deploy, so you should check and test your app to confirm that your newest code is working in production.

### ✅ Front-end Getting Started Checklist

- Have you mapped out a user flow through your app?
- **Wireframes for each interface the user will see**
    - What data will you need on each page or interface? Where is it coming from?
    - What requests will you need to make from the front end?
- Plan out the components and, if you are implementing client-side routing, the routes you think you will need.
- Are you making forms? Discuss data with the backend.
- What assets (e.g. images, logos) will you need?
- General strategy for CSS and design so that you can budget time for it.
    - Are you using a CSS library or framework (e.g. Material UI, Bulma, Tailwind)? What is the general look and feel of your app?
    - Start to think about UI/UX and design.
- Deploy early.
    - Make sure more than one person on your team has access to the Netlify dashboard for your app ([Netlify docs on adding site members](https://docs.netlify.com/accounts-and-billing/team-management/manage-team-members/#manage-site-members)).
    - Plan to keep an eye on your production app.
    - Every time you merge a pull request and the main branch changes, it will trigger a new deploy, so you should check and test your app to confirm that your newest code is working in production.
