# Ops

Includes CI/CD and Continuous Deployment

## Videos

[Continuous Deployment or Continuous Delivery? | When To Release - Dave Farley](https://www.youtube.com/watch?v=mBzDPRgue6s&ab_channel=ContinuousDelivery)

- Continuous Delivery as software always in a releasable state
- Continious Deployment as the pipeline that automatically verifies and deploys software to production
- Some thoughts here about producer-driven releases vs. consumer-driven releases: example of time-sensitive updates for certain applications

## Articles

[QA in the land of Continuous Deployment - Martijn Endenburg](https://medium.com/@martijn.endenburg/qa-in-the-land-of-continuous-deployment-86102938e248)

- Identifies 4 'levels' for releases:
  1. Manual QA before integration and release
  2. Continuous Integration: unit & integration tests on a build server. QA verifies state of software before it's released on Production
  3. Continuous Delivery: automate deployment to acceptance environment. QA still verifies releases, but deployment is semi-automated (push-button deployment)
  4. Continuous Deployment: automatic deployment (no push-button step). QA no longer tests on acceptance environment / approves, requires a change in role
- Three amigos: PO, dev and QA compose acceptance criteria together. Given, then, when structure can be used. Acceptence tests can be automated by the _development_ team. Role of QA is to consider these acceptance tests before development takes place.
- QA still does manual testing, but it's an additional quality control level. Exploratory testing.
