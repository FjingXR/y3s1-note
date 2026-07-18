Chapter 2
Table of Contents

2.1 Project Planning and Estimation

2.2 Project Monitoring and Control

2.3 Selection of Process Models

1

Introduction

• Software project management begins with a set of
activities that are collectively called project planning.
• Before the project start, the software team should
estimate:
✔ the work to be done,
✔ the resources required ( e.g. __ ) , and
✔ the time required from start to finish
• Once these activities are accomplished, the team should
develop a project schedule that
✔ Defines the software engineering tasks and milestones,
✔ Identifies who is responsible for conducting each task, and
✔ Specifies the inter-task dependencies

2

2.1 Project Planning and Estimation

•Project Planning
•Estimations in Projects

3

Project Management Process Group and Knowledge Area Mapping

Initiating

Planning

Executing

M&C

Integration

Develop Project
Charter

Develop PM Plan

Direct & Manage Project Work

• M&C Project Work
• Perform Integrated Change Control

Closing

Close Project or Phase

Scope

Time

Cost

Quality

HR

Plan Scope Management
• Collect Requirements
• Define Scope
• Create WBS

Plan Schedule Management
• Define Activities
• Sequence Activities
• Estimate Activity Resources
• Estimate Activity Durations
• Develop Schedule

Plan Cost Management
• Estimate Costs
• Determine Budget

Plan Quality Management

Plan HR Management

• Validate Scope
• Control Scope

Control Schedule

Control Costs

Perform Quality Assurance

Control Quality

• Acquire Project Team
• Develop Project Team
• Manage Project Team

Communications

Plan Communications Management

Manage Communications

Control Communications

Risk

Identify Risks

Plan Risk Management
•
• Perform Qualitative Risk Analysis
• Perform Quantitative Risk Analysis
• Plan Risk Responses

Control risks

Procurement

Plan Procurement Management

Conduct Procurements

Control Procurements

Close Procurements

Stakeholder

Identify Stakeholders

Plan Stakeholder Management

Manage Stakeholder  Expectation

Control Stakeholder  Engagement

4

Project Planning

2.1 Project Planning and Estimation

Steps in Project Planning

0. Select project

1. Identify project scope

and objectives

2. Identify project
infrastructure

Decompose WBS into smaller,
manageable work packages.

10. Lower-level

planning

3. Analyze project
characteristics

4. Identify the products

and activities

5. Estimate effort for

each activity

6. Identify activity risks

7. Allocate resources

E.g.
• Complexity (simple / complex?)
• Duration (short / long?)
• Quality Requirements (low / high?)
• etc

For each
activity
- e.g. can John handle task A?

If no, how about Susie?

9. Execute plan

8. Review/ publicize

plan

5

Project Plan Content

Project Planning

Introduction

Content of a project plan:
a.
b. Background: including reference to the business case
c. Project objectives
d. Constraints – these could be included with project objectives
e. Method
f. Project products: both deliverable products that the client will

receive and intermediate products

g. Activities to be carried out
h. Resources to be used
i. Risks to the project
j. Management of the project, including

▪ Organizational responsibilities
▪ Management of quality
▪ Configuration management

6

Stakeholders

Project Planning

• People who have a stake or interest in the project.
• Can be categorized as:

o The project team – they are directly involved in doing the project work.
o External to the project team but within the same organization. E.g. the
project leader might need the assistance of the users to carry out system
testing

o External to both the project team and the organization.

Examples:
• contractors who will carry out specific works for the project.
• suppliers who supplies hardware
• customers (or users) who will benefit from the system that the project
implements

• Different types of stakeholders may have different interests. Thus, the
project leader must recognize these different interests and to be able
to reconcile them.

7

Setting Project Objectives
Project Planning

• Among the stakeholders are those who actually own
the project and control the financing of the project.
Hence, they also set the objectives of the project.
• The objectives should define what the project team
must achieve for project success.
• Objectives focus on the desired outcomes of the
project rather than the tasks within it – they are the
post-conditions of the project.

8

Setting Project Objectives
Project Planning

• In order to achieve the goal, we must achieve certain
objectives first.
o i.e., the objectives are steps on the way to achieve a goal.

• An effective objective for an individual must be
something that is within the control of that
individual.

• e.g., an appropriate objective for software developers
would be to keep development costs within a certain
budget.

9

SMART
Project Planning

Well-defined objective should be:
• Specific – The project objective should be clear,
well-defined, and unambiguous.
Obj = To achieve minimum customer satisfaction rating of
8/10 by 30-Jun.
This obj is specific. It clearly states the desired outcome.

Obj = “To achieve higher level
of customer satisfaction.”
Does this obj clearly states the
No
desired outcome?

• Measurable – there should be measures of effectiveness
which tell us how successful is the project.
Customer satisfaction is measurable right?
• Achievable – it must be within the power of the individual
or group to achieve the objective
• Relevant – the objective must be relevant to the true
purpose of the project.
• Time constrained – there should be a defined point in time
by which the objective should have been achieved.
30-Jun is the deadline to achieve the desired outcome

- Project is “something” that you will do/carried out
- Objective is the “desired outcome” that you want to achieve

* Cust satisfaction target = 8/10: achievable?
* If target = 10/10: achievable?

Example 1:

To achieve
minimum customer
satisfaction rating of
8/10 by 30-Jun
through training
customer service
team

Ref: Appendix 2.1
Taxonomy of Project
Definitions

10

Example 2:
(this is not a SMART obj)

To develop a Hotel
Room Booking System
which allowed users to
complete their job which
save a lot of time and
they will like it.

(source: FYP proposal)

Improved Version
To implement a Hotel
Room Reservation
System by 01-05-2026
that will reduce booking
time to 10 mins at a
cost not more than
$100,000.

SMART
Project Planning

This obj did not mention the
amount of time it will help to
saved

Well-defined objectives should be:
• Specific –project objective should be clear, well-defined, and
unambiguous.
(Obj= reduce booking time to 10 mins at a cost not more than $100,000
by 01-05-2026.

This obj is specific. It clearly state the desired outcomes

• Measurable – there should be measures of effectiveness which
tell us how successful is the project.
1) Amount of time (months) taken to complete the proj
3) Amount money spent to complete the project
2) Time (minutes) user spent to complete room booking

This project is considered successful if:
1) Completed not later than 01-05-2026
2) Development cost <= 100K
3) Time to complete booking is <= 10’

• Achievable – it must be within the power of the individual or
group to achieve the objective.

• Relevant – the objective must be relevant to the true purpose of
the project.

- Project is “something” that you will do/carried out
- Objective is the “desired outcome” that you want to achieve

• Time constrained – there should be a defined point in time by
What is the time constraint
which the objective should have been achieved.
of this project? _______
11

Setting Project Objectives
Project Planning

• Among the stakeholders are those who actually own
the project and control the financing of the project.
Hence, they also set the objectives of the project.
• The objectives should define what the project team
must achieve for project success.
• Objectives focus on the desired outcomes of the
E.g.  “To implement a Hotel Room
project rather than the tasks within it – they are the
Reservation System by 01-05-2026 that
post-conditions of the project.
will reduce booking time to 10 mins at a
cost not more than $100,000”

Written in this way allow us to check
how successful is the project team

12

Gantt Chart
Project Planning

• A bar chart where all project tasks are listed in the
left-hand column and the horizontal bars indicate
the duration of each task.
• When multiple bars occur at the same time on the
calendar, task concurrency is implied.
• The diamonds indicate milestones.
• Produces project tables (i.e. a tabular listing of all
project tasks, their planned and actual start and end
dates) which enable you to track progress.

13

Gantt Chart
Project Planning

Milestone (◊) – a
marker use to
help in identifying
group of
activities, set
schedule goals
and monitor
progress

14

Gantt Chart
Project Planning

define the dependencies
between tasks

Project Schedule / Project Table

1
2
3
4
5
6
7
8
9
10

Task no 3 must be
completed before task
no 5 can start

Task no 4 & 5 must be
completed before task
no ___ can start

4,5

8,9

15

Project Schedule + Gantt Chart

Project Planning

16

Program Evaluation and Review Technique (PERT)
Project Planning

Q) How to develop a better time estimates

for each task/activity? OR How to
develop a better time estimates when
there is a high degree of uncertainty
about the individual activity duration
estimates?

 Ans: Use PERT (aka network diagram)

PERT uses 3 estimates for the duration
of each task instead of one!
• Optimistic time
• Most likely time
• Pessimistic time

17

Use Program Evaluation and
Review Technique (PERT) to
develop a better time estimate
for each task

Program Evaluation and Review Technique (PERT)
Project Planning

PERT Step 1: Identify specific activities and milestones

18

Program Evaluation and Review Technique (PERT)
Project Planning

PERT Step 2: Specify Predecessor to sequence project activities

19

Program Evaluation and Review Technique (PERT)
Project Planning

PERT Step 3: Estimate the time for each activity

• Use the 3-time estimates:
(cid:0) Optimistic time (O): the shortest time in which the

activity can be completed

(cid:0) Most likely time (ML): the completion time that has the

highest probability

(cid:0) Pessimistic time (P): the longest time in which the

activity can be completed.

• Then, calculate the expected time using the weighted

average formula.

te = (O + 4*ML + P) / 6

20

Program Evaluation and Review Technique (PERT)
Project Planning

PERT Step 3: Use 3-time est. to est. the time for each activity
calculate the Expected Time (te) for each activity

4.5 weeks is a BETTER
time estimate for activity F

Formula
(O + 4*ML + P) / 6

(3 + 4*4 + 8) / 6 = 4.5

For task/activity F:
Using PERT = 4.5 weeks 🡪 5 weeks

- Without using PERT = __ weeks.
   (based on most likely(ML)

21

Can be completed in 3
weeks instead of 4

Most likely
need 4
weeks

4 weeks is not
possible! 8 weeks
instead

Program Evaluation and Review Technique (PERT)
Project Planning

PERT Step 4: Construct a network diagram
• You can represent both sequential and parallel activities in the diagram.
• Each activity represents a node; arrows to show relationships between

activities.

22

Program Evaluation and Review Technique (PERT)
Project Planning

PERT Step 5: Identify the critical path

• It's the longest path in the network diagram
• Any task on this path is delayed, it will delay the entire project.
• Identifying the critical path is crucial for project managers as it helps in

scheduling, resource allocation, and ensuring the timely completion of a project.

23

Program Evaluation and Review Technique (PERT)
Project Planning

Exercise: Draw this network diagram MANUALLY!

Below is a Network Diagram
generated by Microsoft
Project
1. Click Task
2. Click Gantt Chart
3. Select Network Diagram

24

Program Evaluation and Review Technique (PERT)
Project Planning

A PERT chart illustrates a project as a network diagram

8

8

6

4

4

6

6

6

6

6

25

Estimations in Projects
Project Planning

• Estimating resources, cost and schedule for a software

project requires:
•experience
•access to good historical information (metrics) and
•quantitative predictions.

• Estimation carries inherent risks, and this risk leads to

uncertainty.

• Uncertainty in project planning:

o Project complexity
o Project size
o Degree of structural uncertainty (i.e. the degree to which

requirements have been solidified, the ease with which functions
can be compartmentalized, and the hierarchical nature of the
information that must be processed)

26

Estimations in Projects
Project Planning

To achieve reliable cost and effort estimates:
• Delay estimation until late in the project
• Base estimates on similar projects that have already
been completed
• Use relatively simple decomposition techniques to
generate project cost and effort estimates
• Use one or more empirical models for software cost and
effort estimation

27

Estimations in Projects
Project Planning

Three-point Estimates
(for estimating task/activity duration)
1.

Simple Average
(cid:0) (P+O+ML)/3
(cid:0)

Triangular distribution

2. Weighted Average
(cid:0) (P+O+4ML)/6
(cid:0)

Beta distribution

28

Estimations in Projects
Project Planning

Simple Avg
 (P+O+ML)/3

Weighted Avg
(P+O+4ML)/6

Activity Optimistic

Pessimistic

Most
Likely

Triangular
Distribution

Beta
Distribution

A

B

C

D

E

F

G

H

2

4

4

10

8

6

16

6

6

12

10

22

18

16

26

12

4

8

7

16

13

11

22

10

4

8

7

16

13

11

22

10

4

8

7

16

13

11

22

10

[6+12+(4*10)]/6
= 9.67

(6+12+10)/3
= 9.33

Round UP to the nearest
whole number

29

Ch2: Project Planning, Control & Process Models Selection
Quick Review
2.1 Project

🡪 Create a WBS (WBS is a list of activities to be carried out)
🡪 Estimate the Start Date & End Date for each task/activity (duration=ED - SD)
(cid:0) Set relationship between tasks 🡪 Project Schedule(PS)

Planning and
Estimation

(specify the predecessor)

(PS allows you to view all tasks and the
relationship between tasks)

🡪 Use 3-POINT ESTIMATE to develop a  BETTER time allocation for each

task/activity instead of using a single estimate.

🡪 Draw Network diagram 🡪 To identify critical path

2.2 Project Monitoring and Control

2.3 Selection of Process Models

30

2.2 Project Monitoring and Control

• Tracking the Schedule
• Cost Monitoring
• Project Control - Corrective Actions
• Earned Value Analysis (EVA)

31

Project Management Process Group and Knowledge Area Mapping

Initiating

Planning

Executing

M&C

Integration

Develop Project
Charter

Develop PM Plan

Direct & Manage Project Work

• M&C Project Work
• Perform Integrated Change Control

Closing

Close Project or Phase

Scope

Time

Cost

Quality

HR

• Plan Scope Management
• Collect Requirements
• Define Scope
• Create WBS

• Plan Schedule Management
• Define Activities
• Sequence Activities
• Estimate Activity Resources
• Estimate Activity Durations
• Develop Schedule

• Plan Cost Management
• Estimate Costs
• Determine Budget

Plan Quality Management

Plan HR Management

• Validate Scope
• Control Scope

Control Schedule

Control Costs

Perform Quality Assurance

Control Quality

• Acquire Project Team
• Develop Project Team
• Manage Project Team

Communications

Plan Communications Management

Manage Communications

Control Communications

Risk

Identify Risks

• Plan Risk Management
•
• Perform Qualitative Risk Analysis
• Perform Quantitative Risk Analysis
• Plan Risk Responses

Control risks

Procurement

Plan Procurement Management

Conduct Procurements

Control Procurements

Close Procurements

Stakeholder

Identify Stakeholders

Plan Stakeholder Management

Manage Stakeholder  Expectation

Control Stakeholder  Engagement

32

Tracking the Schedule

2.2 Project Monitoring and Control

Tracking can be accomplished in a number of different ways:
• Conduct periodic project status meetings (each team

member reports progress and problems)

• Compare the actual start date against the planned start date

for each project task listed in the project table …
• Check whether formal project milestones have been

accomplished by the scheduled date

• Evaluate the results of all reviews conducted throughout the

software engineering process

• Use Earned Value Analysis technique to assess progress

quantitatively

• Meet informally with practitioners to obtain their subjective
assessment of progress to date and problems on the horizon

33

Project Control - Corrective Actions

2.2 Project Monitoring and Control

• Project manager needs to monitor project

progress in terms of the time, cost and quality
(triple constraints)

• Control is more than monitoring and finding out
problems, take corrective actions whenever and
wherever needed.

34

Project Control - Corrective Actions

2.2 Project Monitoring and Control

a. Adding more staff
b. Adding different skills
Reassigning tasks
c.
Increasing/decreasing individual supervision
d.
Improving methods of working
e.
Streamlining the process
f.
Changing resource priorities
g.
Re-planning the project
h.
Changing the phasing of deliverables
i.
Increasing/decreasing the number of inspection
j.
Encouraging the team
k.
Introducing incentives
l.
Subcontracting part of the work
m.
n. Negotiating changes in the specification

35

Project Control - Corrective Actions

2.2 Project Monitoring and Control

a. Adding more staff

One of the possibilities when behind schedule

• Will work if a task can be partitioned
(E.g. Interview users to gather requirements)

• Drawback

 - Will incur additional cost
-  May further delay the task because need to

consider communication, learning curve, time to
get-up to speed & etc.

Project Control - Corrective Actions

2.2 Project Monitoring and Control

b. Adding different

skills

• An alternative to adding more staff, consider
adding people with different or greater skills

• When problems need skill/knowledge or staff lack
experience
• Adding experienced or skilled staff to a team may yield

results  e.g Adding a person who is skillful in UI design

Project Control - Corrective Actions

2.2 Project Monitoring and Control

c. Reassigning Task

• No need to add staffs or skills

• Simply switch tasks around as each member has

different strength

• May result in higher productivity or better quality of
work as some are creative, some are thorough, while
some are analytical

• Can make use of the knowledge of characteristics of
the team members to assign tasks that will make use
of their strength

Project Control - Corrective Actions

2.2 Project Monitoring and Control

d. Increasing
individual
supervision

• Problems with the work of members are known
only when they deliver products
• Partitioning tasks and creating smaller
deliverables to exercise quality control more
frequently
• To allow inexperienced/ less confident staff to
obtain guidance

Project Control - Corrective Actions

2.2 Project Monitoring and Control

e. Decreasing
individual
supervision

• Opposite when dealing with experienced staff who

may resent too frequent check up

• May affect personal interest and affect the work quality
• Giving individual responsibility and increase job interest

and motivation for larger deliverables

• Reduces work of supervision and re-channel resourceful

focus

Project Control - Corrective Actions

2.2 Project Monitoring and Control

f. Improving methods

of working

• Besides the work itself, need to consider the

suitability of methods for the tasks

• E.g. using Joint Application Development (JAD)

approach to reconcile what seemed to be mutually
exclusive requirements between different users,
staging workshop where all users can come together
to thrash out the differences during analysis stage
• Using 4th GL to obtain users interface requirements

Project Control - Corrective Actions

2.2 Project Monitoring and Control

g. Streamlining the

process
(Make the process more
efficient or simplified the
process or remove
unnecessary activities)

• Some tasks like quality control may be
bureaucratic and time-consuming
• Will be aggravated if the procedures or processes
are vague
• Streamline processes by removing unnecessary
activities and using standardized forms and
process (e.g. using standardised change
request(CR) form or download CR form from the
intranet)

Project Control - Corrective Actions

2.2 Project Monitoring and Control

h. Changing resource

priorities

• Access to some important resources may be
limited and created bottlenecks
• Need to negotiate for better access or find
alternative environment/facilities in which work
can proceed
• Examine the project critical path to relocate the
priorities of access

Project Control - Corrective Actions

2.2 Project Monitoring and Control

i. Re-planning the

project

• Problems evaluation may show some fundamental flaws in

the way project has been planned

• Although embarrassing, it is critical, project manager has to

rework the plan

• Some tasks dependencies become clear after the work has

started

• Need to note while new plans remove problems of old plan

may introduce new risks

• A re-appraisal of the risks should be part of the re-planning

process

Project Control - Corrective Actions

2.2 Project Monitoring and Control

j. Changing the
phasing of
deliverables

• Short of a complete revision of plan, it may prove effective by

changing the phasing of the deliverables

• Planning may show as one end-product but analysis may reveal

that the product can be partitioned into several discrete
elements

• Some discrete elements may have higher priorities and may be
possible to consider phased delivery to concentrate on more
urgent requirements

• May also consider parallel working e.g. design overlap with

analysis

• May introduce new risks and proper appraisal is needed

Project Control - Corrective Actions

2.2 Project Monitoring and Control

k. Decreasing the

number of
inspections

• Only IF inspections (assessment) are uncovering
an acceptably low no. of defects
• Else problems will arise later and doesn’t result in
any positive effects

Project Control - Corrective Actions

2.2 Project Monitoring and Control

l. Increasing the
number of
inspections
(This is to solve
quality problems)

• For critical systems and IF intermediate deliverables

are less satisfactory

• Or there is a high level of defects on completed

deliverables

• To ensure errors are discovered earlier and rectified

more quickly

• May delay the project when no. of inspections

increases

Project Control - Corrective Actions

2.2 Project Monitoring and Control

m. Encouraging
the team

• Project fatigue may arise (lower productivity, increased
absenteeism, resignations, complaints, etc)
• Actions may include:

• refocusing on team’s achievements to rekindle enthusiasm
• organize social events in company time to engender a sense of

team spirit

• redistribution of work to provide development opportunities
• a team building exercise of some sort
• reducing the size of deliverables (at the end may be larger!)

Project Control - Corrective Actions

2.2 Project Monitoring and Control

n. Introducing
incentives

• Depending on the organization, the project manager may
or may not be able to offer financial incentives
• But incentives may be in other form, e.g. time off,
recognition, etc.
• For multiple team, inter-team competition may be
considered but practiced with care

Project Control - Corrective Actions

2.2 Project Monitoring and Control

o. Subcontracting
part of the
work

• Despite all the tools and techniques, project may still not
on schedule
• Project manager may consider sub-contracting out the
tasks to those with special skills/ facilities
• But responsibility will still be with the PM
• Must make sure the contractors work to the required
standards

Project Control - Corrective Actions

2.2 Project Monitoring and Control

p. Negotiate

changes to the
specification

• When all else fail, may negotiate to change the
specification (may be the original objective is too
ambitious for the time or money

• Alternatively, may resort to phased delivery with major
functions being delivered first (Not usually well received
but better than to fail the project totally

Project Control - Corrective Actions

2.2 Project Monitoring and Control

a. Adding more staff
b. Adding different skills
Reassigning tasks
c.
Increasing/decreasing individual supervision
d.
Improving methods of working
e.
Streamlining the process
f.
Changing resource priorities
g.
Re-planning the project
h.
Changing the phasing of deliverables
i.
Increasing/decreasing the number of inspection
j.
Encouraging the team
k.
Introducing incentives
l.
m.
Subcontracting part of the work
n. Negotiating changes in the specification

What else
can be
added here?

52

Previous lesson

2.1 Project Planning and Estimation

Project Planning

Before the project start, estimate:
✔ the work to be done,
✔ the resources required ( e.g. __ ) , and
✔ the time required from start to finish

2.2 Project Monitoring and Control

• Tracking the Schedule
• Project Control – Take Corrective
Actions if project is behind schedule
• Cost Monitoring

2.3 Selection of Process Models

Estimation

• 3-point estimate

- Simple Average (P+O+ML)/3
- Weighted Average (P+O+4ML)/6

• Draw network diagram, Identify critical path

53

Monitoring Cost
2.2 Project Monitoring and Control

• Cost/expenditure monitoring provides an indication of the
effort that has gone into (or at least been charged to) a
project.
• A project might be on time but only because more money
has been spent on activities than original budgeted.
• A cumulative expenditure chart provides a simple method
to compare planned costs against actual costs.
o By itself it is not particularly meaningful, e.g. the expenditure

chart could illustrate a project that is running late or one that is
on time but has shown substantial cost savings.

o Thus, we need to take into account the current status of the

project activities before attempting to interpret the meaning of
recorded expenditure.

54

Monitoring Cost
2.2 Project Monitoring and Control

(Compare planned cost against actual cost)

estimated cost to
complete a project

t

Diagram shows, at time t,
ACTUAL COST < PLANNED
COST (i.e. actual amount paid <
planned amount to be paid)

Is there substantial costs savings?

Use Earned Value Analysis
(EVA) to draw conclusion

Track cumulative expenditure

actual amount of
$ spent in the
project

55

Earned Value (EV)  Analysis
2.2 Project Monitoring and Control
• EV analysis is a refinement of cost monitoring.
    (takes into account the project progress and schedule)
• After doing EV analysis you will be able to check whether:
• 1. project cost has exceeded its budget
• 2. project is behind schedule or ahead of schedule
• EV Analysis is based on assigning a “value” to each task (as
identified in the WBS) based on the original expenditure
forecasts. This assigned value is called planned value (PV).
• PV = the price agreed upon by a contractor to do the unit of
work OR value of the work planned to be completed
• EV = the actual value of work completed
• A task that has not started,  the EV = 0,
   EV = PV when it has been completed

…

56

Earned Value (EV)  Analysis
2.2 Project Monitoring and Control

5 Techniques for Crediting or assigning EV to a Project
• 0/100 technique: a task is assigned a value of 0 until it is
completed, at which it is given a value of 100% of the
budgeted value.

(EV=0 when the job starts, when the job is finished EV=PV)
• 50/50 technique: a task is assigned a value of 50% of its value
as soon as it is started and then given a value of 100% once it’s
completed.

(EV=50% of the PV when the job starts, when the job is finished EV=PV)

• 75/25 technique: a task is assigned a value of 75% of its value
as soon as it is started and then given a value of 25% once it’s
completed.

(EV=75% of the PV when the job starts, when the job is finished EV=PV)

• milestone technique: a task is given a value based on the

achievement of milestones that have been assigned values as
part of the original budget plan.

(assign a value to EV based on milestone achievemt

• % complete: the EV is based on the % of the project that has

been completed.

(assign a value to EV based on percentage of work completed

57

Step 1: Create the baseline budget

Earned Value Analysis

• The baseline budget

(i.e. planned value, PV)
is created based on the
project plan.

• Shows the forecast

growth in earned value
through time.

• May be measured in
monetary values or
person-hours (or
workdays).

• This example uses the
0/100 technique for
crediting EV to the
project.

58

Step 2: Monitor the earned value
• Having created the baseline budget, the next task is to monitor earned value

Earned Value Analysis

(EV) as the project progresses.

• This is done by monitoring the completion of tasks (or activity starts and

milestone achievements in the case of other crediting techniques).

• In addition, the actual cost (AC) of each task is also recorded.

Earned Value Management (EVM) – Basic Metrics

✔ Planned Value (PV): Value of the work planned to be

completed

✔ Budget at Completion (BAC): Budget for the whole

project

✔ Earned Value (EV): Actual value of the work
completed (5 ways to assign a value to EV)

✔ Actual Cost (AC): Actual cost incurred for the work

completed

59

Step 3: Calculate Performance Statistics

Earned Value Analysis

(after knowing PV and EV)

Cost Variance (CV)
= EV – AC
• negative indicates cost has

exceeded its budget

• positive means …

Schedule Variance (SV)
= EV – PV
• negative indicates project is behind

schedule

• positive means …

60

Task

Estimated
Duration (month)

Estimated
Cost ($)

Status

EV

EV = actual value of work completed
= estimated cost * status of completion

A

B

C

D

E

F

G

H

I

J

K

L

M

N

O

Total

2

3

1.5

2.5

PV (value
2
of work
0.5
planned to
1.5
be
completed
2
)

1

2.5

3

1.5

2

3

1

29

70,000

27,000

82,000

25,000

30,000

48,000

100,000

10,000

45,000

17,000

32,000

12,000

10,000

24,000

12,000

544,000

100%

85%

62%

48%

23%

16%

0

0

0

0

0

0

0

0

0

0

Exercise #1
AC (actual cost)
You  are  now  in  the  9th  month  of  29
months  project.  As  of  today,  you  have
spent  RM198,000  based  on  the  invoice
reconciliation.  You  need  to  provide  data
to  Mr.
Sponsor),
specifying  if  the  project  status  is  healthy
or  unhealthy.  You  are  using  EVM/EVA
technique  to  provide  the  sponsor  with
this information.

(Project

Jordon

BAC (budget at completion)
i.e. project budget

61

Task

Estimated
Duration (month)

Estimated
Cost ($)

Status

EV

EV = actual value of work completed
= estimated cost * status of completion

A

B

C

D

E

F

G

H

I

J

K

L

M

N

O

Total

2

3

1.5

2.5

PV (value
2
of work
0.5
planned to
1.5
be
completed
2
)

1

2.5

3

1.5

2

3

1

29

70,000

27,000

82,000

25,000

30,000

48,000

100,000

10,000

45,000

17,000

32,000

12,000

10,000

24,000

12,000

544,000

100%

85%

62%

48%

23%

16%

0

0

0

0

0

0

0

0

0

0

AC (actual cost)

Exercise #1(R)
You  are  now  in  the  9th  month  of  29
months  project.  As  of  today,  you  have
spent  RM198,000  based  on  the  invoice
reconciliation.  You  need  to  provide  data
to  Mr.
Sponsor),
specifying  if  the  project  status  is  healthy
or  unhealthy.  You  are  using  EVM/EVA
technique  to  provide  the  sponsor  with
this information.

(Project

Jordon

BAC (budget at completion)
i.e. project budget

62

Exercise #1
You  are  now  in  the
9th  month  of  29
months  project.  As
of  today,  you  have
RM198000
spent
based
the
on
invoices
reconciliation.  You
need to provide data
Jordon
to  Mr.
Sponsor),
(Project
the
specifying
is
project
healthy
or
unhealthy.  You  are
using
EVM/EVA
technique to provide
the
sponsor  with
this information.

if
status

Answer

Task

Estimated
Duration
(month)

Estimate
d Cost
($)

Status

EV

A

B

C

D

E

F

G

H

I

J

K

L

M

N

O

Total

PV

2

3

1.5

2.5

2

0.5

1.5

2

1

2.5

3

1.5

2

3

1

29

70,000

27,000

82,000

25,000

30,000

48,000

100,000

10,000

45,000

17,000

32,000

12,000

10,000

24,000

12,000

544,000

100%

85%

62%

48%

23%

16%

0

70,000

22,950

50,840

12,000

6900

7680

0

Actual value of work
completed in the 9th
month

0

0

0

0

0

0

0

0

You are now in the 9th month,
AC (actual cost) = 198,000
Budget At Completion (BAC) = 544,000

PV = 70k + 27k + 82k + 25k = 204,000 (9
months)

EV = (70k*100%) + (27k*85%) + (82k*62%)
+ (25k*48%) + (30k*23%) + (48k*16%)
= 170, 370

SV (schedule variance)= EV - PV
=170,370 – 204,000
= -33,630

value of work
planned to be
completed in the
9th month

SV is negative means that the project is behind
schedule (In the 9th month, actual value of
work completed is < value of work planned
to be completed)

63

Exercise #2
You  are  now  in  the
9th  month  of  29
months  project.  As
of  today,  you  have
RM198,000
spent
based
the
on
invoices
reconciliation.  You
need to provide data
Jordon
to  Mr.
Sponsor),
(Project
the
specifying
is
project
healthy
or
unhealthy.  You  are
using
EVM/EVA
technique to provide
the
sponsor  with
this information.

if
status

(using different set of data)

Task

Estimated
Duration
(month)

Estimate
d Cost
($)

Status

EV

A

B

C

D

E

F

G

H

I

J

K

L

M

N

O

Total

PV

2

3

1.5

2.5

2

0.5

1.5

2

1

2.5

3

1.5

2

3

1

29

70,000

27,000

82,000

25,000

30,000

48,000

100,000

10,000

45,000

17,000

32,000

12,000

10,000

24,000

12,000

544,000

100%

100%

100%

100%

50%

50%

0

0

Actual value of work
completed in the 9th
month

0

0

0

0

0

0

0

0

You are now in the 9th month,
AC (actual cost) = 198,000
Budget At Completion (BAC) = 544,000

PV = 70k + 27k + 82k + 25k = 204,000 (9
months)

EV =  243,000

SV (schedule variance)= EV - PV
= 243,000 – 204,000
= 39,000

value of work
Planned to be
completed in the
9th month

- SV is positive means that
the project is ahead of
schedule (In the 9th
month, actual value of
works completed is >
value of works planned
to be completed)

- MORE works have been
completed than planned!

This good news
or bad news? _
64

Exercise #2
You  are  now  in  the
9th  month  of  29
months  project.  As
of  today,  you  have
RM198.000
spent
based
the
on
invoices
reconciliation.  You
need to provide data
Jordon
to  Mr.
Sponsor),
(Project
the
specifying
is
project
healthy
or
unhealthy.  You  are
using
EVM/EVA
technique to provide
the
sponsor  with
this information.

if
status

(using different set of data) (con’t)

Task

Estimated
Duration
(month)

PV
Estimate
d Cost
($)

A

B

C

D

E

F

G

H

I

J

K

L

M

N

O

Total

2

3

1.5

2.5

2

0.5

1.5

2

1

2.5

3

1.5

2

3

1

29

70,000

27,000

82,000

25,000

30,000

48,000

100,000

10,000

45,000

17,000

32,000

12,000

10,000

24,000

12,000

544,000

Status

100%

100%

100%

100%

50%

50%

0

0

0

0

0

0

0

0

0

0

You are now in the 9th month,
AC (actual cost) = 198,000

EV

PV = 70k + 27k + 82k + 25k = 204,000 (9 months)

EV =  243,000

SV = 39,000

CV (cost variance) = EV- AC
= 243,000 – 198,000
= 45,000

Actual amount paid

Actual value
of work
completed

- CV is positive, it means that the
project is under budget.
- In the 9th month, actual value of work
completed is > amount paid

- However, if CV is negative, it means that
amount paid is > actual value of work
completed!

65

Exercise #3
You  are  now  in  the
9th  month  of  29
months  project.  As
of  today,  you  have
RM198.000
spent
based
the
on
invoices
reconciliation.  You
need to provide data
Jordon
to  Mr.
Sponsor),
(Project
the
specifying
is
project
healthy
or
unhealthy.  You  are
using
EVM/EVA
technique to provide
the
sponsor  with
this information.

if
status

(again using different set of data)

Task

Estimated
Duration
(month)

PV
Estimate
d Cost
($)

A

B

C

D

E

F

G

H

I

J

K

L

M

N

O

Total

2

3

1.5

2.5

2

0.5

1.5

2

1

2.5

3

1.5

2

3

1

29

70,000

27,000

82,000

25,000

30,000

48,000

100,000

10,000

45,000

17,000

32,000

12,000

10,000

24,000

12,000

544,000

Status

100%

100%

100%

100%

100%

100%

100%

100%

100%

100%

100%

100%

100%

100%

0%

0

* You are now in the 28th month
* AC (actual amt paid) = 544,000

PV = 70k + 27k + … + 24k = 532,000

EV = 70k + 27k + … + 24k = 532,000

CV (cost variance) = EV- AC
= 532,000 - 544,000
= -12,000

Actual
amount paid

Actual value
of work
completed

- CV is negative, it means that amount

paid is > actual value of work completed!
- On the 28th month, amount paid is more
than actual value of work completed
(544K vs 532K)

Q) How much more are needed to pay

complete the project? _______

12K

EV
70,000

27,000

82,000

25,000

30,000

48,000

100,000

10,000

45,000

17,000

32,000

12,000

10,000

24,000

Total amount to complete the project will be 556K

Cost Variance & Schedule Variance

Earned Value Analysis

Earned Value Management (EVM)
Variances

Cost Variance (CV)
= EV – AC (negative indicates
budget is exceeded)
(at time t, amount paid is > actual value of
work completed)

Schedule Variance (SV)
= EV – PV (negative indicates
behind schedule)
(At time t, actual value of work completed is <
value of work planned to be completed)

67

Tut 2

You are managing a project with 12th month’s durations, and now you are in
10th month. The planned value (PV) for the 10th month is RM148,000. As of
today, the total amount has been paid out is RM145.000 with 80% of the works
completed. The budget at completion (BAC) for this project is RM 180,000.
Calculate SV = EV - PV and CV = EV - AC.

PV = 148K (value of work
planned to be completed in the
10th month)

AC = 145K (total amount paid
in the 10th month, amount of work
completed = 80%)

EV =80% of works completed x BAC

       =0.8  x 180K = 144K

SV = 144K – 148K = -4K
CV = 144K – 145K = -1K

Q) Project progress is good? __

68

Tut 2b You are managing a project with 12th month’s durations, and now you are in 10th

month. The planned value (PV) for the 10th month is RM148,000. As of today, the
total amount has been paid out is RM145.000 with 90% of the works
completed. The budget at completion (BAC) for this project is RM 180,000.
Calculate SV = EV - PV and CV = EV - AC.

PV = 148K (value of work
planned to be completed in the
10th month)

AC = 145K (total amount paid
in the 10th month, amount of work
completed = 90%)

EV=90% of works completed xBAC

= 0.9 x 180K = 162K

SV = 162K – 148K = 14K
CV = 162K – 145K = 17K

Q) Project progress is good or bad? _

69

Earned Value Management/ Earned Value analysis

Earned Value Analysis

Schedule Variance (SV) = EV – PV
-negative indicates project is behind
schedule (at time t, actual value of
work completed is < value of work
planned to be completed)

- Positive indicates ?

Cost Variance (CV) = EV – AC
 - negative indicates budget is

exceeded ((at time t, amount paid >
actual value of work completed)

- Positive indicates ?

70

Select the right corrective actions to be taken
when  SV is negative:

a. Adding more staff
b. Adding different skills
Reassigning tasks
c.
Increasing/decreasing individual supervision
d.
Improving methods of working
e.
Streamlining the process
f.
Changing resource priorities
g.
Re-planning the project
h.
Changing the phasing of deliverables
i.
Increasing/decreasing the number of inspection
j.
Encouraging the team
k.
Introducing incentives
l.
Subcontracting part of the work
m.
n. Negotiating changes in the specification

Earned Value Management/ Earned Value analysis

Earned Value Analysis

Schedule Variance (SV) = EV – PV
-negative indicates project is behind
schedule (at time t, actual value of
work completed is < value of work
planned to be completed)

- Positive indicates ?

Cost Variance (CV) = EV – AC
 - negative indicates budget is

exceeded ((at time t, amount paid >
actual value of work completed)

- Positive indicates ?

71

Select the right corrective actions to be taken
when  CV is negative:

a. Adding more staff
b. Adding different skills
Reassigning tasks
c.
Increasing/decreasing individual supervision
d.
Improving methods of working
e.
Streamlining the process
f.
Changing resource priorities
g.
Re-planning the project
h.
Changing the phasing of deliverables
i.
Increasing/decreasing the number of inspection
j.
Encouraging the team
k.
Introducing incentives
l.
Subcontracting part of the work
m.
n. Negotiating changes in the specification

2.3 SELECTION OF PROCESS MODELS

Effort

Identify
a Need

Develop
proposed
solution

Perform the project

Terminate
the project

RFP Proposal

SDLC

Time

• Waterfall models
• Prototyping Model
• Rapid Application

Development (RAD)
• Incremental Model
• Spiral model
• Component-based

development

Waterfall Model

2.3 SELECTION OF PROCESS MODELS

Feasibility study

User requirements

Analysis

• ‘Classical’ model of system development
• Also known as one-shot or once-through model.
• There is a sequence of activities working from
top to bottom.
• A later stage may reveal the need for some extra
work at an earlier stage. However with a large
project, try to avoid reworking tasks previously
thought to be completed.

System design

Program design

Coding

Testing

Operation

73

Waterfall Model

2.3 SELECTION OF PROCESS MODELS

Feasibility study

User
requirements

Analysis

System design

Program design

• Advantages:

• Creates natural milestones at the end of each phase.
• Can easily check on project progress.
• Suitable for project where requirements are well
defined and the development methods are well
understood.

Coding

Testing

Operation

• Disadvantages:

• Not suitable for project with uncertainty.
(not recommended when user requirements are not well defined)
• Not flexible – reluctant to go back to previous stage.

74

Prototyping Model

2.3 SELECTION OF PROCESS MODELS

Listen to
customer

• Evolutionary prototype

• The prototype is built in stages, with each stage

adding more features and refinements.

• It will evolve into the final system

Customer test
drives
prototype

Build/revise
prototype

• Throw-away prototype

• The prototype is built rapidly to explore ideas

and gather feedback.

• It is discarded after the necessary information is

gathered; it is not used in the final system.

75

Prototyping Model

2.3 SELECTION OF PROCESS MODELS

Listen to
customer

Customer test
drives
prototype

Build/revise
prototype

• Advantages:

•
•

•

Useful when user requirements  are uncertain.
Functional/valuable in designing system’s UI
(data-entry screen, reports or Web pages).
Encourages user’s(customer’s) involvement.

• Disadvantages:

•

•

Prototyping may skip essential steps in system
development e.g. skip the testing phase in system
development
Prototyping can be time-consuming if several
iterations are needed to refine the design. This can
lead to longer project timelines.
Q) Worth the time spent ? ___

76

Rapid Application Development (RAD)

2.3 SELECTION OF PROCESS MODELS

• Incremental software development process model that

emphasizes short development time.

• System can be produced within 60-90 days, if

requirements and project scope are well defined

• Each RAD team will take a major

function/component/module (component to be
accomplished within 3 months) and then integrated to
form a whole.

Requirements planning

Architecture

Design

Design

Design

Construc
t-
ion

Construc
t-
ion

Constru
ct-
ion

Integration

Delivery

77

Business modeling

Data modeling

Process modeling

Application
generation

Testing & turnover

Rapid Application Development
2.3 SELECTION OF PROCESS MODELS

• Business modeling:

• What information drives the business process?
• What information is generated?
• Who generates it? Where does the information go?
• Who processes it?

• Data modeling:

• The information flow is refined into a set of data objects with attributes and

relationships between objects.

• Process modeling:

• Processing descriptions are created for adding, modifying, deleting, or retrieving

a data object.

• Application generation:

• Reuse existing program components/create reusable components.

• Testing and turnover:

• Reused components have been tested before and thus reduce testing time.
• Need to test integration of different components

78

Rapid Application Development

2.3 SELECTION OF PROCESS MODELS

• Advantage

• Drawbacks:

System can be
completed in a short
period of time
(within 60-90 days)
because several RAD
teams are
developing the
system
simultaneously

• For large but scalable projects, RAD
requires large number of resources
to create the right number of RAD
teams

• Requires developers and customers

committed to the rapid-fire
activities.

• Not suitable for system that cannot

be modularized.

• Not suitable when technical risks are

high: Examples

• New system use new technology
• New software needs to integrate with

existing system.

79

Incremental Model

2.3 SELECTION OF PROCESS MODELS

• Linear sequential model + prototyping
• The software is designed, implemented, and
tested in increments (smaller portions or
modules) NOT delivering the entire system at
once.
(Delivery is module by module i.e. one module at a time)
• Each increment builds on those that have already
been delivered.

80

Incremental Model (e.g)
2.3 SELECTION OF PROCESS MODELS

• Linear sequential
model + prototyping
• The software is
designed,
implemented, and
tested in increments
(smaller portions or
modules) NOT
delivering the entire
system at once.
• Each increment builds
on those that have
already been delivered.

(User  registration module)

Deliver User
registration module

Product
listing
module

Shopping
cart module

Payment
module

Add Product listing module
to existing system

Add Shopping
cart module to
existing system

Add payment
module to
existing system

(system completed)

81

Component-based Development

2.3 SELECTION OF PROCESS MODELS

• A software development approach that uses well-defined
independent software components.
• These components are then integrated to create a
complete system.

•Example

o User Registration Component: accept registration and verify user login

o Search Product Component: Allows users to search for products.

o Shopping Cart Component: add, update and remove items in shopping cart.

o Payment Gateway Component: Processes payments

o Using pre-built functionalities and integrate them to form
a complete system instead of building these features from
scratch

82

Spiral Model

2.3 SELECTION OF PROCESS MODELS

Define new features
(e.g. add fund transfer)

Planning

Define basic requirements
(e.g. login & chk bal)

Identify potential risks
(e.g. potential hacking)
Risk analysis

Identify potential risks
associated w/ fund trf
(e.g. ___ )

Project entry
point axis

add new
features

Customer: I want
a banking mobile
app…

Customer evaluation

Construction & release

Dev the mobile app

Dev the new features

engineering

Design the mobile app

Design the new features

83

Spiral Model

2.3 SELECTION OF PROCESS MODELS

• A greater level of detail is considered at each
stage of the project.
• System to be implemented is considered in
more detail in each sweep in the loop.
• Each sweep terminates with an evaluation
before the next iteration is embarked upon.
• Key point: to reduce risk associated with
the project

84

Spiral Model

2.3 SELECTION OF PROCESS MODELS

• As this evolutionary process begins, the software engineering

team moves around the spiral in a clockwise direction, beginning
at the center.

• The first circuit around the spiral might result in the development
of a product specification; subsequent passes around the spiral
might be used to develop a prototype and then progressively more
sophisticated versions of the software.

• Each pass through the planning region results in adjustments to

the project plan. Cost and schedule are adjusted too.

• PM decides number of iterations required to complete the

software.

85

Project Process Model Selection
Models

Project scope

Development
Time

Budget Man power

User
Requirement

User

Waterfall

Large

Long

High

Many staffs

Well defined

Less involved

Prototyping

Small to medium

Flexible

Low

Few staffs

Uncertain

Highly involved

Rapid Application
Development
(RAD)

System can be
partitioned/
modularised

60-90 days

High

Incremental

Flexible/complex

Short

Low

Many staffs
(e.g. each team to
handle 1 module)

Lack of staff
(few staffs)

Well defined

Highly involved

Well defined

Highly involved

Spiral

Component-based
development

Large-scale, risky
system

System that can
be partitioned/
componentized

Long

Short

High

Need Experts

Uncertain

Highly involved

Low

Less staffs

Well defined

Highly involved

86

Summary

2.1 Project Planning and

Estimation

2.2 Project Monitoring and

Control

2.3 Selection of Process

Models

87


