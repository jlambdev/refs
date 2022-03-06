# Ops

Includes CI/CD and Continuous Deployment

## Videos

[Continuous Deployment or Continuous Delivery? | When To Release - Dave Farley](https://www.youtube.com/watch?v=mBzDPRgue6s&ab_channel=ContinuousDelivery)

-   Continuous Delivery as software always in a releasable state
-   Continious Deployment as the pipeline that automatically verifies and deploys software to production
-   Some thoughts here about producer-driven releases vs. consumer-driven releases: example of time-sensitive updates for certain applications

[The Role Of QA in Agile Software - Dave Farley](https://www.youtube.com/watch?v=XhFVtuNDAoM&ab_channel=ContinuousDelivery)

-   Continuous Delivery challenges assumptions about people's roles (esp. QA)
-   It means software must always be in a releasable state
    -   PO/PM must identify granular changes instead of large grandiose plans
    -   Devs needs to be able to release at any time
    -   QAs _are not gatekeepers for releasing to production_ anymore
-   Deployment pipeline determines when something is releasable
-   Checks QA needs to perform, without being gatekeepers to production:
    -   Does the software do what we expect it to do?
    -   Does it still do everything else?
-   Frequency that we do testing is important: the more & earlier the better
    -   Aim: _test as features are being developed_
    -   In Lean this approch is called 'One Piece Flow'
    -   Test every change, not in batches
    -   "you can't inspect quality into a system, you build it into a system"
-   Leverage pair programming & automated testing (especially TDD)
    -   composing tests immediately before writing code is as efficient and high quality as we can get
-   There are 2 problematic scenarios with the traditional gatekeeper approach:
    1. Quality seen as _vital_ and it becomes a bottleneck, slowing the pace of change. We want to work in small, fast, definitive steps with good monitoring.
    2. Delivery prioritised over quality. QA are tasked with defending quality and they are forced to let some bugs slip through to production.
-   QA becomes guides and experts on quality & testing for the rest of the team. Not after we've finished, but before we begin.
    -   QA should be part of the development team
    -   The _team_ spots mistakes as they happpen
    -   Inspection happens as new features are introduced into the system
-   On the user story level have a kickoff meeting (3 amigos)
    -   Product owner: need of feature, goal to achieve
    -   Devs (in this example he gives 2 devs together): those who will do pair programming
    -   QA: advisor & manual testing required
        -   QA & devs explore cases where we can be confident the system does what it needs to do, asking the PO what to do in exception scenarios
        -   _team comes up with executable specifications_ which form the definition of Done; QA will identify scenarios that devs are likely to miss
        -   anyone can write these tests; _developers_ are responsible for making them pass
-   Manual testing is useful in the right context; manual _regression testing_ is not valuable in any context
    -   we want to automate as much regression testing as possible
    -   humans are good at _exploratory_ testing
    -   ideally everyone is working at the same time: QA inspects things as they are being developed
-   More rewarding way of working for QAs

## Articles

[QA in the land of Continuous Deployment - Martijn Endenburg](https://medium.com/@martijn.endenburg/qa-in-the-land-of-continuous-deployment-86102938e248)

-   Identifies 4 'levels' for releases:
    1. Manual QA before integration and release
    2. Continuous Integration: unit & integration tests on a build server. QA verifies state of software before it's released on Production
    3. Continuous Delivery: automate deployment to acceptance environment. QA still verifies releases, but deployment is semi-automated (push-button deployment)
    4. Continuous Deployment: automatic deployment (no push-button step). QA no longer tests on acceptance environment / approves, requires a change in role
-   Three amigos: PO, dev and QA compose acceptance criteria together. Given, then, when structure can be used. Acceptence tests can be automated by the _development_ team. Role of QA is to consider these acceptance tests before development takes place.
-   QA still does manual testing, but it's an additional quality control level. Exploratory testing.
