Chapter 3

Quality
Management &
Assurance

Chapter 3

Quality
Mgmt
 &
Assurance

From chapter 1

Budget

E.g. 1:

Consequences of low quality ...
Knight Capital’s Faulty Trading Software
(August 2012)

Knight Capital had to give a big payout for its buggy trading
software: $440 million. The software’s algorithm was designed
to enact automatic orders over several days but  a bug caused
the software to make all the orders in 1 hour, buying and
selling stock with a loss of up to 15 cents per share. Ultimately,
Knight Capital lost 4x its 2011 proﬁt and was acquired by a
rival company (Getco LLC) in Dec 2012.

3

E.g. 2:

Consequences of low quality ...
Google’s Nest’s Smart Thermostat Software Bug
(January 2016)

A device used to control temp within a device.
• Activate cooling when temp rises too high
• Activate heating when temp falls below

certain point

When a thermostat is deactivated, it will
not be able to control the device temp.

E.g. unable to activate cooling when temp
rises too high

A December software update contained a bug which deactivated
the thermostat and drained the device’s battery. Even when
developers ﬁxed the problem, they were left with annoyed
customers who were less than happy to undertake the 9-step
process to reboot the device ...

4

Consequences of low quality ...

E.g. 3:

5

Software with Low Quality

Give 1 example ____________

6

Software with Low Quality

E.g. 4:

Existing manual system is simple and straight forward
[only needs 5-10 mins to ﬁll-in the expense
reimbursement form] but using the new computerised
system it took much longer to do the same).

7

T.O.C

3.1 Quality Concepts & Principal Activities

3.2 Quality Planning & Quality Control

3.3 Process and Product Quality Relationship

3.4 Techniques to Help Enhance Software Quality

3.5 Quality Management and Costs

3.6 Quality Assurance and Standards

8

3.1 Quality Concepts & Principal Activities

• The Importance of Software Quality
• Defining Software Quality
• Principal Quality Activities

o QA

o QP

o QC

9

3.1 Quality Concepts & Principal Activities

The Importance of Software Quality

● Organizations are relying more on computer systems

- high quality software will ...

● Most safety-critical systems have built-in software

- high quality software will ensure that system functions as expected in ALL situations.

● Quality retains customers and increases proﬁts
● Quality is essential for international marketing

10

3.1 Quality Concepts & Principal Activities

Deﬁning Software Quality

• Quality simply means a product

meet its specification.

● The subjective quality of a software

system is largely based on its
non-functional characteristics. This
reflects practical user experience

11

Software Quality
Attributes
● Quality simply means a

product meet its
specification.

● The subjective quality of a software
system is largely based on its
non-functional characteristics. This
reflects practical user experience
When planning for quality,
select the most important
quality attributes for the
software being developed.

Appendix 3.1 ISO/IEC 25010 Quality Model & Attributes

Deﬁning Software Quality

12

Software Quality
Attributes
● Quality simply means a

product meet its
specification.

● The subjective quality of a software
system is largely based on its
non-functional characteristics. This
reflects practical user experience
When planning for quality,
select the most important
quality attributes for the
software being developed.

Appendix 3.1 ISO/IEC 25010 Quality Model & Attributes

Deﬁning Software Quality

√

Q) Which
quality
attributes are
important for
an
e-commerce
website?

Q) Can you
suggest
one more
____ ?

√

√

√
√

13

Conflicting Software
Quality Attributes
● It is not possible for any system to
be optimized for all of these
attributes

E.g., increasing SECURITY may
lead to lower performance

● There is a tension between

customer quality requirements
(efficiency, reliability, etc.) and
developer quality requirements
(maintainability, Portability)

Appendix 3.1 ISO/IEC 25010 Quality Model & Attributes

Deﬁning Software Quality

TO ACHIVE A
HIGH LVL OF
PERFORMANCE
EFFICIENCY AND
HIGH LVL OF
SECURITY AT
THE SAME = NO

14

When planning for quality, select the most important quality attributes for the software
being developed then develop a quality specification for the product!

Desired quality attribute

Software Quality Speciﬁcation
Qual.Attri.

Deﬁne the quality attribute.

:

Scale

Test

Min/Max
acceptable

Target
range

Now

:

:

:

:

:

Specify the unit of measurement for the quality attribute

Describe the method or process used to measure quality attribute

Specify the lowest/highest acceptable value for the quality attribute. Values
below/above this threshold means the product should be rejected.

Specify the desired range of values for the quality attribute

The current value of the quality attribute.

15

Desired quality
attribute

quality attribute
definition

Deﬁning Software Quality

Software Quality Speciﬁcation (E.g. 1)

Maintainability
(Modifiability)

Degree to which a system can be effectively and efficiently modified without introducing
defects or degrading existing product quality

Scale

Test

Min acceptable

Target range

Now

Specify the unit of measurement for the quality attribute
(e.g length of variable name)

Describe the method or process used to measure the quality attribute
1. Count the no of characters used in variable name (take a sample of 6 programs)
2. Calculate the average length (e.g.)

= 24/6 = 4)

(2+3+3+4+4+8)
 6

Specify the lowest acceptable value for the quality attribute. Values below this threshold
means the product should be rejected. Min acceptable length = 5 characters

Specify the desired range of values for the quality attribute
Desired range = 6 – 10 characters

The current value of the quality attribute. 4 characters

Q) Is the length of var
name up to the desired
level to achieve a high
degree a modifiability?

16

Desired quality
attribute

quality attribute
definition
Software Quality Speciﬁcation

(E.g. 2)

Deﬁning Software Quality

Usability
(User Error
Protection)

Scale

Test

Min
acceptable

Target range

Now

Degree to which a system protects users against making errors.

The unit of measurement for the quality attribute. % err.protection (0 to 100), 0% indicates no
error protection and 100% means the system has complete protection against user errors
Describe the method or process used to measure the quality attribute. (i) Examine all input screens. (ii) Count
no of input ﬁelds with constraints[A], (iii) no of input ﬁelds w/o constraints but with helpful labels or
instructions[B] and no of input ﬁelds w/o constraints and w/o helpful labels or instructions[C].
(iv) Percentage of protection= ([A+B]/[A+B+C] * 100%).  (Note: A+B+C = total no of input ﬁelds in the sys)
Specify the lowest acceptable value for the quality attribute. Values below this threshold
means the product should be rejected. Min acceptable = 80% of protection

Specify the desired range of values for the quality attribute
90% - 100%. This is to enhance user satisfaction.

The current value of the quality attribute.. 70%

Q) Is the system ability
to protect user’s from
making errors up to the
desired level?

17

(E.g. 3a)

Software Quality Speciﬁcation

Q) Has the system(XYZ M.App) under construction met the quality requirement? ____
Usability
(efficiency)

Deﬁnition of “efﬁciency” How quickly a task can be completed

Deﬁning Software Quality

Scale

Test

max
acceptable

Target range

Specify the unit of measurement for the quality attribute.
TIME (in minutes)

Describe the method or process used to measure the quality attribute
1. Run usability test with 10 users.
2. Record time each user took to pay for 2 hours of street parking using the XYZ Mobile App
3. Calculate the average time taken

(Total time taken by 10 users)
 10

Specify the highest acceptable value for the quality attribute. Values above this threshold means
the product should be rejected. Max acceptable time = 1 min

Specify the desired range of values for the quality attribute 0.5 – 1 min
This is to ensure that user will adopt the XYZ Mobile App

Now

The current value of the quality attribute. 1.5 mins (after 2 times of system redesign)

18

Deﬁning Software Quality

Purpose of SQS
to ensures the final
product meets the
desired quality standard

(E.g. 3b)

Software Quality Speciﬁcation

Q) Has the system(XYZ M.App) under construction met the quality requirement? ____
Usability
(efficiency)

Deﬁnition of “efﬁciency” How quickly a task can be completed

Scale

Test

max
acceptable

Target range

Specify the unit of measurement for the quality attribute.
TIME taken (in minutes)

Describe the method or process used to measure the quality attribute
1. Run usability test with 10 users.
2. Record time each user took to pay for 2 hours of street parking using the XYZ Mobile App
3. Calculate the average time taken

(Total time taken by 10 users)
 10

Specify the highest acceptable value for the quality attribute. Values above this threshold means
the product should be rejected. Max acceptable time = 1 min

Specify the desired range of values for the quality attribute 0.5 – 1 min
This is to ensure that user will adopt the XYZ Mobile App

Now

The current value of the quality attribute. 0.6 mins (after 3 times of system redesign)

19

Revisit (E.g. 1)

Software Quality Speciﬁcation

Deﬁning Software Quality

Maintainability
(Modifiability)

Degree to which a system can be effectively and efficiently modified without introducing
defects or degrading existing product quality

Scale

Test

Min/max
acceptable

Target range

Specify the unit of measurement for the quality attribute
(e.g.1 length of variable name)

e.g.2 Depth of nested if statement

Measurement will give you an
Describe the method or process used to measure the quality attribute
INDICATOR on the “Degree to
1. Count the no of characters used in variable name (in all programs)
which a system can be effectively
2. Calculate the average length
and efficiently modified without
Specify the lowest/highest acceptable value for the quality attribute. Values below/above this
introducing defects or degrading
threshold means the product should be rejected. 5 characters
existing product quality”
Specify the desired range of values for the quality attribute
6 – 10 characters

(2+3+3+4+4+8)
 6

= 24/6 = 4)

Now

The current value of the quality attribute. 4 characters

20

3.1 Quality Concepts & Principal Activities

Principal Quality Activities

● Software Quality Management (SQM)’s 3 main activities:

1. Quality Assurance (QA): to develop an organizational framework
(procedures & standards) that will lead to high quality of software.

2. Quality Planning (QP): to select appropriate procedures and

standards from the framework and adapt to a speciﬁc software
project.

3. Quality Control (QC): to execute processes to ensure that software

development follows the quality procedures and standards.

● In project mgmt, the QA team should be independent from the development

team so that they can take an objective view of the work products.

21

3.1 Quality Concepts & Principal Activities

• The Importance of Software Quality

• Defining Software Quality

- developing a software quality
specification for the product

• Principal Quality Activities

o QA

o QP

o QC

3.2  Quality Planning &
Quality Control

•

Introduction

• Quality Plans

• Quality Control

22

3.2 Quality Planning & Quality Control

Introduction

● QA establishes the infrastructure that supports solid
software engineering methods, rational project
management and quality control actions.

● QC encompasses a set of software engineering actions that
help to ensure that each work product meets its quality
goals.

● Some organizations produce quality plans for each project.

23

3.2 Quality Planning & Quality Control

Quality Plans

A quality plan

● Speciﬁes the desired product qualities and how these are

assessed

(e.g. IF usability is the desired quality, it may be assessed
through user testing. Target = minimum 90% task success rate

● Should indicate which organizational standards should be

applied (and where necessary, deﬁne new standards to be used)

24

Quality Plans Structure

● Product introduction
● Product plans
● Process descriptions
● Quality goals
● Risks and risk management
Note:

- quality plans should be short, succinct documents
-

if they are too long, no one will read them.

Quality Plans

25

3.2 Quality Planning & Quality Control

Quality Control (QC)

● QC involves monitoring the software development process
to ensure that QA procedures and standards are being
followed.

● The deliverables from the software development process
are checked against the deﬁned project standards during
the QC process, either using quality reviews and/or
automated software assessment.

26

Quality Control (QC)

Quality Reviews

● Quality reviews involve a group of people

checking part or all of a software process, system
or its documentation to ﬁnd potential problems.

● Outcome of the review
- List of problems found
- author to do corrections

27

Quality Control (QC)

Review Type

Purpose

Design or program
reviews

To ﬁnd errors in the requirements, design or code.

Progress reviews

To ﬁnd out project progress and report to management

Quality reviews

To carry out a technical analysis or product components
or documentation to ﬁnd mismatches between the
speciﬁcation and the component design, code or
documentation and to ensure that deﬁned quality
standards of the organization have been followed.

28

3.1 Quality Concepts & Principal
Activities

3.2 Quality Planning & Quality Control
3.3 Process and Product
Quality Relationship
3.4 Techniques to Help Enhance
Software Quality

3.5 Quality Management and Costs

3.6 Quality Assurance and Standards

3.3 Process and Product Quality Relationship

● In general, the quality of the development
process directly affects the quality of
delivered products. The quality of the
product can be measured and the process is
improved until the proper quality level is
achieved.

● In manufacturing systems, there is a clear

relationship between the production process
and product quality. However, quality of
software is highly influenced by the
experience of software engineers. In
addition, it is difficult to measure certain
software quality attributes and to tell how
process characteristics influence these
attributes.

29

3.4

Techniques to Enhance
Software Quality

•

Inspections

• Cleanroom software development

• Software quality circles

• Lessons learnt report

30

3.4 Techniques to Enhance Software Quality

Inspections

● Inspections can be applied to documents produced at any

development stage.

● When a piece of work is completed, copies are distributed to

co-workers who examine the work, noting defects/problems. A
meeting then discusses the work and a list of defects requiring rework
is produced.

● E.g. of works that may be examine:

-   Table design (e.g.  No of ﬁelds in a table – too little?, too many?)
- Program codes (e.g. length of variable names, _______, etc)
- ______________

● Inspections (aka Fagan method) was pioneered by an IBM employee

31

3.4 Techniques to Enhance Software Quality

Beneﬁts of Inspections

● Very effective in removing superﬁcial
errors. (e.g. Register, Sign-up For An
Account)

● It can enhance team spirit

● Helps spread good programming practices
as the participants discuss speciﬁc pieces
of code.

● Helps developers to produce better

structured and self-explanatory software.
32

https://www.google.com/search?q=inspection+clipart&client=firefox-b-d&source=lnms&tbm=isc
h&sa=X&ved=2ahUKEwidoNfyxvj7AhXc-TgGHUo-DBwQ_AUoAXoECAIQAw&biw=1525&bih=6
87&dpr=0.9

Inspections

Principles of the Fagan method
● Inspections are carried out on all major deliverables.

● All types of defect are noted - not just logic or function errors.

● Inspections can be carried out by colleagues at all levels except the very top.

● Inspection meetings do not last for more than 2 hours.

● Inspections are carried out using a predeﬁned set of steps.

● The inspection is led by a moderator who has been trained in the technique.

● The other participants have deﬁned roles (e.g., one person will act as a recorder and

note all defects found, and another will act as reader and take the other
participants through the document under inspection).

● Have a checklists in the fault-ﬁnding process.

● Material is inspected at an optimal rate of about 100 lines an hour.

● Statistics are maintained so that the effectiveness of the process can be monitored.

33

Cleanroom Software Development

3.4 Techniques to Enhance Software Quality

● Improved from structured programming: de-component complex
system so that each component has only one entry and exit point
which make testing easier and more precise.

● Aims to avoid defect rather than detect and repair them:

○ Use incremental development approach
○ Use statistical testing/veriﬁcation

● Rationale for incremental approach:

○ User requirement changes are inevitable
○ New requirements are added later; Main modules given ﬁrst (gradually

increase the implemented functionality)

○ Each new function will be tested and measured against pre-deﬁned
standards. If fail to meet the standards, go back to design phase.

34

Cleanroom Software Development

3.4 Techniques to Enhance Software Quality

3 separate teams:
● Speciﬁcation team

○ obtains the user requirements and a usage proﬁle estimating the

volume of use for each feature in the system

● Development team

○ develops the code in increments but does not do testing on the

program code produced

● Certiﬁcation team

○ carries out testing which is continued until a statistical model shows
that the failure intensity has been reduced to an acceptable rate

35

3.4 Techniques to Enhance Software Quality

Cleanroom Beneﬁts & Weaknesses
Beneﬁts
○ Lower number of errors

Weaknesses

(codes are develop by dev-team but testing are
carried out by certiﬁcation-team)

○ Software of higher quality

(lower no of errors means higher software quality)

● Lower cost

(lower no of errors also means there will be less
rework, less rework is a cost saving)

○ Project on schedule
due to less rework

● Works well with skilled

and committed
engineers only.

● This approach is
conﬁned to a few
technologically
advanced
organizations only.

36

3.4 Techniques to Enhance Software Quality

Software Quality Circle

● The aim of Japanese quality circle approach is to examine
and modify the activities in the development process in
order to reduce the number of errors that they have in their
end-products.

● Testing and Fagan inspections can assist the removal of

errors, but the same types of error could occur repeatedly
in successive products created by a faulty process. By
uncovering the source of errors, this repetition can be
eliminated.

37

Software Quality Circle

https://www.google.com/search?q=quality+circle+clipart&tbm=isch&ved=2ahUK
EwjsroakzPr7AhXV_TgGHSkFDyIQ2-cCegQIABAA&oq=quality+circle+clipart&g
s_lcp=CgNpbWcQA1DaCVjaCWDlC2gAcAB4AIABNYgBaZIBATKYAQCgAQGq
AQtnd3Mtd2l6LWltZ8ABAQ&sclient=img&ei=-IiaY-zSHdX74-EPqYq8kAI&bih=6
87&biw=1525&client=firefox-b-d

- A faulty process will
repeatedly produce
faulty products.

- Quality Circle is to FIX

THE PROCESS so that
the same types of error
will not occur again

Quality Circle
● A quality circle is a group of 4 to 10 volunteers working in

the same area (e.g. software development dept). They meet
for about an hour a week to identify, analyze and solve their
work-related problems.
○ One volunteer is the group leader.
○ There could be an outsider, a facilitator, who can advise on

procedural matters.

● In order to make the quality circle work effectively, training

needs to be given.

● Together, the group

○ selects a pressing problem that affects their work;
○ Identify the cause of the problem, and
○ Decide on a course of action to remove the problems.

38

3.4 Techniques to Enhance Software Quality

Lessons Learnt Reports

● Written by the project manager as soon as possible after

the completion of the project.

● Includes

○ reﬂect on the performance of the recently completed project

when the experience is still fresh, and

○ identify lessons to be applied to future projects.

● However, one frequent problem is there is often very little

follow-up on the recommendations of such reports, as there is
often nobody within the organization with the responsibility and
authority to do so.

39

Quick Review…
3.4
4 Techniques to
Enhance/Improve Software
Quality

• Inspections
• Cleanroom software development
• Software quality circles
• __________________

40

3.5 Quality Management & Costs

• Quality Management
• Costs of Quality
• Categories of Quality Costs
•

41

3.5 Quality Management & Costs

Quality Management

is to ensure that the required level of quality is
achieved in a software product.
○ At the organizational level, it is concerned with establishing a
framework of organizational processes and standards that will
lead to high-quality software.

○ At the project level, quality management

■ involves the application of specific quality processes and checking that

these processes have been followed.

■ concerned with establishing a quality plan for a project. The quality plan

should set out the quality goals for the project and define what processes
and standards are to be used

Quality management and software development (Figure 24.1 ref 3, pg 653)

42

Quality Management (cont’d)

3.5 Quality Management & Costs

e.g analysis

design

code

test

implement

- Quality

management
processes are to
check on the
software
development
process.

… to ensure that standards and procedures are followed and

the product meets quality requirements

Quality management and software development (Figure 24.1 ref 3, pg 653)

43

Costs of Quality

3.4 Techniques to Enhance Software Quality

Costs of
quality

= Cost of achieving

+  Cost of low quality

quality
(costs incurred in
performing
quality-related
activities
e.g. ___________ )

software
examples
● Rework to correct an error
● Resolve complaint
● Provide customer support
●

etc

44

3.4 Techniques to Enhance Software Quality

Categories of Quality Cost

The costs of quality can be divided into

a. Prevention Costs

b. Appraisal Costs

c. Failure Costs

45

Categories of Quality Cost

3.4 Techniques to Enhance Software Quality

Prevention Costs
Costs related to performing:

● mgmt activities - To plan and coordinate

all QA and QC  activities

● technical activities  - To develop

complete requirements & design models

● To conduct training associated with the

above activities

Appraisal Costs
Costs to:

● Conduct technical

reviews

● Test products

● Collect data and
report inspection

The goal of all these activities are to ensure that a project is error-free or
within an acceptable range

46

c. Failure Costs

Internal Failure costs
Examples

○ Costs to correct design errors

○ Costs to correct program errors

External Failure costs
Examples

o Resolving customer complaint
○ Handling product return and replacement

○ Providing help line support

○ Managing poor reputation and loss of business

Categories of Quality Cost

Costs incurred prior
to product delivery

Costs incurred after
the product has been
delivered to customers

47

3.4 Techniques to Enhance Software Quality

Categories of Quality Cost

Costs of quality:
a. Prevention Costs

• Management activities - to plan and coordinate all QA and QC

activities

• Technical activities  - to develop complete requirements and

design models

• To conduct training associated with these activities

b. Appraisal Costs

• Conduct technical reviews
• Test products
Internal Failure costs
• Collect data and report inspection
• Costs to correct design errors, Costs to correct program errors

Q) Which cost is the

most
costly/expensive
to a software
company?

How to avoid
“Failure Costs”?

c. Failure Costs
External Failure costs
• Resolving customer complaint, Handling product return and replacement, Providing

help line support, Managing poor reputation and loss of business

48

to develop an organisational framework (procedures &
standards) that will lead to high quality of software.

3.6 Quality Assurance &

Standards

• Quality  Standards
•

ISO/IEC 25010:2011

ISO 9001 Standards Framework

•
• Quality Culture

49

3.6 Quality Standards

Quality Standards

Quality standards are sets of
guidelines, systems, methods,
requirements, and specifications followed
by an organization to ensure consistent
process, product and service quality.

● Quality standards deﬁne the required
quality of a product or process.
● Standards play an important role in

quality management.

● Standards may be international,

national, organizational or project
standards.

The Importance of Quality Standards
● To ensure that products, processes and
services meet customer expectations
and/or comply with regulatory
requirements.

● Encapsulation of best practice - avoids

repetition of past mistakes.

● They are a framework for deﬁning what
quality means in a particular setting, i.e.
the organization’s view of quality.
● They provide continuity - new staff can
understand the organization by
understanding the standards that are
used.

50

Quality Standards

Product & Process Standards

● Process standards - deﬁne the processes that should be

followed during software development
○ Include deﬁnitions of speciﬁcation, design and validation
processes, process support tools and a description of the
documents that should be written during these processes.

● Product standards - apply to the software product being

developed including its documentation
○ Include document standards (e.g. the structure of requirements

documents, documentation standards, coding standards)

51

Product & Process Standards

Quality Standards

Process Standards
(processes that should be followed
during software development)

Product Standards
(standards that apply to the software
product being developed incl. its
documentation)

Conduct design review

Design review form

Submission of new code

Requirements document structure

Version release process

Method header format

Project plan approval process

Java programming style

Test recording process

Project plan format

Change control process

Change request form

52

Problems with Standards

Quality Standards

● They often involve a lot of bureaucratic form ﬁlling

● They may NOT seen to be relevant and up-to-date by

software engineers

● If they are unsupported by software tools, tedious form ﬁlling is
often involved to maintain the documentation associated with
the standards

53

Standards Development

Quality Standards

● Involve practitioners in development - engineers should understand

the rationale underlying a standards.

● Review standards and their usage regularly - standards that are
outdated will have reduced credibility among practitioners

● Detailed standards should have specialized tool support - excessive
clerical work is the most signiﬁcant complaint against standards.

54

3.6 Quality Assurance & Standards

ISO/IEC 25010:2011

The ISO/IEC 25010:2011 Systems and software engineering - Systems
and software Quality Requirements and Evaluation (SQuaRE) - System
&  software quality models deﬁnes
● A quality in use model composed of 5 characteristics*  that relate to the
outcome of interaction when a product is used in a particular context of
use.

● A product quality model composed of 8 characteristics* that relate to
static properties of software and dynamic properties of the computer
system
*some of which are further subdivided into sub-characteristics

Note: this standard replaced the ISO/IEC 9126 Software engineering-Product quality standard.

55

ISO/IEC 25010:2011

ISO/IEC 25010:2011 can beneﬁt these activities:

● Identifying software & system requirements
● Validating the comprehensiveness of a requirements deﬁnition
● Identifying software and system design objectives
● Identifying software and system testing objectives
● Identifying quality control criteria as part of QA
● Identifying acceptance criteria for a software product
● Establishing measures of quality characteristics in support of

these activities

56

ISO/IEC 25010:2011

ISO/IEC 25010:2011 Quality in Use Model

● Effectiveness
● Efﬁciency
● Satisfaction

○ Usefulness
○ Trust
○ Pleasure
○ Comfort

● Freedom from risk

○ Economic risk mitigation
○ Health & safety risk mitigation
○ Environmental risk mitigation

● Context coverage

○ Context completeness
○ Flexibility

Refer to https://www.iso.org/obp/ui/#iso:std:iso-iec:25010:ed-1:v1:en for details.

57

3.6 Quality Assurance & Standards

The ISO 9001 Standards Framework

● An international set of standards that can be used as a basis

for developing quality management systems.

● ISO 9001, the most general of these standards, applies to
organizations that design, develop and maintain products,
including software.
○ It sets out general quality principles, describes quality
processes in general and lays out the organizational
standards and procedures  that should be deﬁned. These
should be documented in an organizational quality
manual.

58

ISO 9001 Standards Framework

ISO 9001 Characteristics

● ISO 9001 is not itself a standard for software development but is

a framework for developing software standards

● It sets general quality principles, describes quality processes in
general, lays out the organizational standards and procedures
that should be deﬁned. These must be documented in an
organizational quality manual.

● To be conformant with ISO 9001, a company must have

deﬁned the types of processes shown in the following ﬁgure
and procedures that demonstrate that its quality processes
are being followed.

59

ISO 9001 Core Processes

ISO 9001 Standards Framework

60

ISO 9001 & Quality Management

ISO 9001 Standards Framework

61

ISO 9001 Standards Framework

ISO 9001 Certiﬁcation

● Quality standards and procedures should be documented in

an organizational quality manual.

● An external body may certify that an organization’s quality

manual conforms to ISO 9000 standards.

● Some customers require suppliers to be ISO 9000 certiﬁed.

62

3.6 Quality Assurance & Standards

Quality Culture

● Organizations should aim to develop a quality culture where

everyone responsible for software development is
committed to achieving a high level of product quality.
● Teams should be encouraged to take responsibility for the
quality of their work and to develop new approaches to
quality improvement.

● They should support people who are interested in the

intangible aspects of quality and encourage professional
behavior in all team members.

63

Summary

3.1 Quality Concepts & Principal Activities

3.2 Quality Planning & Quality Control

3.3 Process and Product Quality Relationship

3.4 Techniques to Help Enhance Software Quality

3.5 Quality Management and Costs

3.6 Quality Assurance and Standards

64


