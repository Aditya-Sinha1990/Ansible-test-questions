# TechOps Technical Questions

## DevOps

1. Why do you think more and more companies are embracing "DevOps"?

- In today's rapid changes and constant upliftiing of customers/user experience in shortest possible time with minimal downtime, devops came to rescue.
  I can say this is a culture which bridges the gap between Dev and Ops team and expedite the SDLC to a great extent providing secured, automated, flexible
  development. It gives business a better view of blockers and improvise almost instantly at any stage, a perfect way to picture the complete lifecycle from 
  planning, building, testing, deploying and planning for new updates.
	From NASA to Netflix, Youtube to a young company wants to have this kind of fast, flexible and more collobarative agile approach which gives a maximum
 output with help of a stable automation and clear communication between various teams.


## VCS

2. Describe any VCS branching strategies that you have used.
- In Recent past, while adding new feature of our terraform code to create RDS and Elasticache, I cam accross features/feature-name.
  eg: Adding a new feature/file/code to master with RDS.tf and Redis.tf and naming the branch with Service Now Request Number.
  secondly hotfix/description branching startegies where I need to make changes in ec2 values and placing behind ALB; newly created ec2.
  lastly, bugfixes/description, fixing error with security group for newly created AWS resources with help of terraform. In this startegy, I needed to make minor
  changes, debugging and correcting. All changes are reviewed before merging to master.
   

3. Which VCS tool are you most comfortable with?
- Git Enterprise/ Github.com

4. Using Git, describe how you would squash the last N commits into a single commit, preserving any commit messages.
- "git rebase -i HEAD~N" #can help to merge all commits into single by placing the head and avoiding all the cluter of commit log that git merge gives.
   or
- "git reset --soft HEAD~N && git commit"
  "git merge --squash HEAD@{1}"

## CI/CD

5. Explain the difference between CI and CD?
- CI-Continous Integration helps to maintain integration of your code into and from SVC multiple times in a day without waiting, giving you continous builds for every 
  code base changes in master. It is more faster and reliable way of development. Providing 
  1. Catching issues early in development phase.
  2. It's cheaper and cost effective
  3. Faster Delivery
  4. Frequent commits, code consolidation, fast builds and faster testing.
  example- Jenkins, Bamboo (My Top Picks)

- CD- Continous Deployment helps to deploy your tested and passed application to a pre-prod and or prod Environment. Keeping your application/code deployable
  at all times in secured and faster manner. As we are having multiple builds and push, making sure, it goes through UAT and once passed, to have the application
  ready to be deployed in pre-prod and or prod environment. 
  We can also have control using Continous Delivery, where after testing we can use manual intervention for final prod deployment or 
  can have continous deployment startegy by automating direct deployment to prod once UAT is Passed.
  example - Octopus Deploy is one of the best tool I have used to deploy Nugget packages with help of environemnt specifics targets.


6. What metrics would you monitor to ensure that your CI pipeline was effective?
- Automation metrics like Code Coverage, number of failed or succeeded builds, total number of builds
- Time to complete each stage and final build time.
- Code Metrics like changes of code size and code duplication.
- Test Metrics like number of unit tests per story, time to fix the tests. 
- Analyzing Output of pipeline run. 


## Security

7. What benefits does TLS have over SSL?
- TLS (Transport Layer Security) is to encrypt and authenticate the computers involved in any communication through any network or internet itself.
  SSL (Secure Socket Layer) is used for same purpose, a cryptographic protocol, however, it is an older version. Most of the IT Companies prefer TLSv1.2.
  At the end we all try to give our users most secured and reliable application as we need to work with personal informations and confidential data.
  Having said that, TLS/SSL Cetificates gives a validation to your application by doing a Extended or Organization or Domain Validation. We can use Certificates
  with both protocols mentioned above. 
  The difference lies in their method and versions. When an older protocol SSL uses public and private keys, TLS works with TLS layers like Record Protocol and
  Handshake Protocol of TLS. TLS first contact the server and then changes to a secure communication once the initial handshake is successful. Where in SSL trial
  and error or spoofing keys is possible and hacker can attempt to duplicate any of the key. TLS is better as it check through this constraints. 
 

8. An audit has been run at your company and a number of API credentials have been discovered in source control.  What steps would you take to secure
these credentials and ensure there is no longer a risk to the company?
 - Using Coach or vault for storing these credentials and calling them at the time of running, without having to save them in codebase. A vault can be used to
   securely provide sensitive details and runs it when needed. Access to it can be temporarry role based or through ssh verification of any integration tool. 

9. Explain the difference in behavior when trying to connect to a port that is protected by iptables with a DROP rule opposed to a REJECT rule.
 - The primary difference is the way it responds to a package. DROP is best rule for unauthorised/unknow attempts trying to get some info periodically.
   REJECT rule reponds to a package with an ICMP destination-unreachable error while DROP does not which gives out information about which ports are closed
   or open by droping the packet right away without responding anything and wait till timeout.
   However, DROP considerably slows down the application reponse for genuine users too.
   

## Incident Management

10. What is an SLI?  What is it used for?  How does it differ from an SLA?
- SLI is Service level Indicator giving best measurement which enterprise service provider uses for their goals.
  Whereas Service Level Agreement is a contract between enterprise service provider with their customer's to provide service availablity and performance.
  The service provider needs to collect metrics based on SLI, and monitor the thresholds of metrics so that it won't break SLA. In practical, the SLIs are
  the metrics in the monitoring system and SLA defines the penalty that service provider should pay in an event of service unavailability for pre-defined 
  period of time.
                  The SLA and SLI are based on such assumption that is the service will not be available 100%  Instead, we guarantee that the system will be available 
  greater than a certain number, for example, 99.4% or 99.6%.
  Examples of SLI - Availablity of uptime of service, cosnistency and durability of data
  Example of SLA penalty- partial refund of service fee, additional subscription time added for free.
  

11. After an incident has been remediated a post-mortem is called.  What is the purpose of a post-mortem?  What do you think the most important 
outcomes of a post-mortem are?
- Incident is something that got captured and needs to checked based on it's priority. Once it is rectified, post-mortem or retrospec for that incident by doing
  a RCA-root cause analysis, reason for the incident. I believe most important part of post-mortem is to make more relaible and effective application and 
  avoiding any such incidence in future and providing best user experience. Being proactive is important in SDLC and hence each incident needs RCA, documentation
  containing details, cause, remedies, steps should be recorded.

## Containers

12. Can you name 3 major advantages of containerization (e.g. Docker) over virtualization (e.g. vSphere)?
- Three major advantages that one can think over containerization over virtualization:
  1. Process Isolation: Freedom to develop in isolation without having to settle in machine efficiency.
  2. High Scalability : As they share same base OS unlike virtualization which makes a heavy duty machine.
  3. Overall Productivity : Faster startup time and service.

13. What are the benefits of a container orchestration platform such as K8 or ECS?
- A good example will be a ticketing website which is hosting a major event and server usages will go sky high if we are placing a ticket sale.
  As many companies are starting to use Docker as their main infrastructure and delivery mechanism, orchestration frameworks become the heart of the system and affects   the way we develop, ship, run and update software.
  In such scenarios; having Auto-Scaling group with AMIs in place and using ECS service or Kubernetes swarm will help to keep the application in place and gives a best
  user experience during high traffic. Overall best user experience, best business outcomes in respect to Returns on Investment/Sales, high service availablity.


## Finally...

14. How would you prepare for a migration of a SQL database from a hosted data centre to the cloud?
- AWS/cloud providers are providing best and better service availability in terms of SQL database. They are highly 
  available, costeffective and secured too. 
- Choosing best suitable migration technology - Forklift or Hybrid
- We need to estimate the usages and future enhancements based on metrics like connection, number of available database,  type of application, Database parameters.
- RDS or Aurora MySql is best replacerment for native/on-prem SQL database.   
- If we have 2 TB storage with 16 GB RAM, we can use a T2.xlarge to m4.large scale.
- Keeping primary and replica in two different Aavailablity zone
- Keeping Database in secured private subnet in your hosted VPC with secured allowed connection only to limited 
  users/systems.
- Challenges:
  1. Selecting best suitable database infrastructure in cloud
  2. Migrating terabytes of data
- Initialization
  1. Correct Infrastructure
  2. Verify the format, schema of current database
  3. Setting up point in time by marking before taking the snapshot.
  4. Time calculation  = Number of Days = (Total Bytes)/(Megabits per second * 125 * 1000 * Network Utilization * 60 
                         seconds * 60 minutes * 24 hours)
  5. Taking assssitance from cloud provider if required like AWS Snowball device or Direct Connect
  6. Estimating downtime and Team collaboration. 
  
