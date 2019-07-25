# Beanstalk-blue-green-deployment


When an application is developed and deployed having two separate, but identical, environments — blue and green — this deployment method increases availability and reduces risk.


Blue/green deployment on the AWS platform provides a safer, less stressful way to upgrade production software. Let’s think of a v1 production environment “blue.” Now, set up a second environment labeled “green” that is running v2 of our software. Once we validate the green environment, we can quickly switch traffic from the blue to the green environment. At this point, we can choose to retain or dispose of the blue environment.

Once we bring the green environment up, we can validate the new software before going live. Then, we start shifting traffic away from the blue environment and send it to the green one. Normally, we do that using weighted DNS resolution because it gives us an easy way to push more traffic to the green environment or revert traffic back to the blue environment in case of issues.
Benefits of Blue/Green Deployment

    If the validation tests of the green environment fail before you start sending real traffic, then we can dispose of the environment without ever having affected the live blue production environment.
    If we start switching a small proportion of traffic from blue to green and encounter serious issues, then we can quickly switch back to blue and restore service within minutes. This process is sometimes called canary analysis: you test that the new deployment works in a real-world scenario with a small set of your users.
    We can easily take advantage of newer, more powerful, or cheaper servers by simply launching the newer server types in your green environment, validating them, and then cutting over.
    We can also take advantage of Auto Scaling to optimize costs. You can allow the size of the fleet of servers in your green environment to grow gradually as you shift more traffic to it, while the size of the blue fleet will shrink as it handles less traffic.

AWS has tools and services to make zero downtime deployments :-

AWS Elastic Beanstalk, a platform as a service (PaaS) that supports most popular development platforms and languages. If your application doesn’t require a very customized platform environment to operate, this is a great, easy to use service. It also offers zero downtime deployments.

If your application has a more complex multi-tier architecture, AWS OpsWorks allows you to model complex decoupled applications. It trades in some of the ease of use of Elastic Beanstalk for increased flexibility. A great feature that makes blue/green deployment easy is the ability to clone a stack and create a copy of your blue stack as a baseline for your green one. Learn how to get started using OpsWorks.
