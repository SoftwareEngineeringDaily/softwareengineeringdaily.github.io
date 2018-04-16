---
title: Pull Requests
category: Backend
order: 3
---

### Submitting a Pull Request

* When you submit a PR, please ask [Jason](https://github.com/jasonify), [Keith](https://github.com/TheHollidayInn), and [Jeff](https://github.com/crablar) to review it.
* *Keep pull requests small!* This makes it easier for us to accept your code. 
* Smaller PRs (1-3 files) help avoid bugs.

### Deployment

The backend is continuously deployed.

Once a pull request is accepted, it is pulled into the master branch, which builds in a Heroku staging environment called [sedaily-backend-staging](https://sedaily-backend-staging.herokuapp.com/).

After testing it manually, we promote it to our [Heroku production environment](https://software-enginnering-daily-api.herokuapp.com/).
