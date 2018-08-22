---
title: Pull Requests
category: Monitoring
order: 2
---

### Submitting a Pull Request

* When you submit a PR, please ask [Andrew](https://github.com/andrewmarklloyd), [Jason](https://github.com/jasonify), and [AbdulBasit](https://github.com/abdulbasitkay) to review it.
* *Keep pull requests small!* This makes it easier for us to accept your code. 
* Smaller PRs (1-3 files) help avoid bugs.

### Deployment

The API is continuously deployed. Once a pull request is accepted, it is pulled into the master branch, which builds in a Heroku environment at [sedaily-devops](https://sedaily-devops.herokuapp.com/api/v1/docs).

The InfluxDB instance that the API connects to is deployed to AWS EC2. Grafana, the open source software for time series analytics is deployed to the same instance. You can view dashboards at [AWS EC2](http://ec2-34-216-71-74.us-west-2.compute.amazonaws.com/).
