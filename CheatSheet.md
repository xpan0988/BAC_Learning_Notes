##### Week1:

**Tips:**
Software specification defines what the system is meant to do

Validation means checking that the system does what the customer wants

verification means checking that does the product builds in right way

Extended period of time it took to develop a system was a cause for project failure

Costs escalated and requirements change was the trigger for agility

Coding is  the most number of defects introduced

System Test is e the most number of defects found

real working code is more valuable than documents



A software process defines a lifecycle of activities (specification,

design/implementation, testing/validation, evolution)



**Waterfall Model**: A linear, phase-driven model with sequential stages –

Requirements → Design → Implementation → Testing → Maintenance

**Advantages**: simple to understand, clear milestones\[7].

**Disadvantages**: inflexible to change; problems detected late may require costly backtracking\[8].

Waterfall suits projects with well-understood, Changes are expensive once later phases are reached, stable requirements but struggles with rapid change\[9]\[10]



**V-Model**: An extension of Waterfall emphasizing testing. For each development phase there is a corresponding test phase.Each development stage has an associated test plan, ensuring verification and validation

steps mirror development, left side represents development phases (requirements, system design, architecture, module design, coding) and the right side represents corresponding test phases (unit, integration, system, acceptance testing)



**Spiral Model**: An iterative, risk-driven process. Development passes through

repeated loops (spirals), each containing planning, risk analysis, engineering and evaluation phases This model focuses on early identification and mitigation of risks and is suited for large, high-risk projects.

**development is organized in loops addressing**:

1\) Objectives and alternative solutions,

2\) Risk analysis and resolution,

3\) Development and verification,

4\) Review and planning for the next cycle\[20]\[22].

The project repeatedly goes through these stages, mitigating risks and refining requirements with each iteration



**Agile Model**: A family of “light-weight” iterative and incremental methods focused on rapid delivery of working software and responsiveness to change\[24].

In general, plan-driven vs. agile: Plan-driven (waterfall-like) processes plan everything in advance and resist change, whereas agile plans continuously and welcomes requirement changes



**Agile Manifesto (2001): Articulates core values favoring individuals and interactions,**

**working software, customer collaboration, and responding to change over corresponding**



**Other Models**: Rational Unified Process (RUP) (a heavy-weight iterative framework combining elements of

other models.





##### Week2:

**Tips:**

Centralised version control is better than local version control

N files committed into repository, N blobs created



Software artifacts (code, documents, etc.) must be managed and versioned

Version Control Systems (VCS) track changes to files over time

so that specific versions can be recalled and changes by multiple people merged



**Local VCS**: Simple databases (on one computer) to track file revisions



**Centralized VCS (CVCS)**: A single central repository, Examples: CVS\*\*(Optimistic concurrency (copy-modify-merge)),\*\* SVN. Multiple users can work concurrently

**Advantages**: Everyone sees a single latest version, simple administration

**Disadvantage**: Central server is a single point of failure; requires network access; branching is heavy-weight. Merging conflicts can be cumbersome



**Distributed VCS (DVCS)**: Each user has a full copy of the repository (including history). Examples: Git, Mercurial

**Advantages**: Fast local operations, no single failure point, easy branching and merging], allows various workflows



**Git Fundamentals**: Git is a widely used DVCS. It treats data as snapshots(snapshot-based storage)

**Key properties**:

Local operations: Almost every operation (commits, diffs, logs) is done locally

Integrity: Every file and commit is checksummed (SHA-1 hash) –data is immutable and referenced by hash

Three states: Modified (file changed, not yet committed), Staged (file marked to include in next commit), Committed (change saved in the repository)



**Git’s structure** includes a Working Directory, Staging Area (Index), and Repository (.git folder)

Workflow basics: Edit files -> git add (stage changes) -> git commit (record snapshot).view status with git status and history with git log



**Branching and Merging in Git**: Branches in Git are movable pointers to commits, default branch is usually master (or main). Creating a new branch (e.g. git branch featureX)just creates a new pointer to the current commit

Switching branches (git checkout branchName)changing the working copy to match that branch’s last commit

**Merging**:bring changes from one branch into another, If the branches evolved independently, Git tries an automatic three-way merge,The developer must manually resolve conflicts

**Fast-forward merge**: has progressed and the target branch has no new commits,  moves the pointer forward



**Distributed Collaboration**: git \*\*fetch\*\* (download new commits from remote), git \*\*merge\*\* or git pull (which does fetch+merge) to integrate them, and git \*\*push\*\* to upload local commits to a remote server

centralized workflow,  Integration Manager or Dictator Lieutenant



Add the upstream remote once, then update local master from upstream and create a new feature branch from it



##### Week3:

**Tips**:
git push origin local:remote means push local branch to the remote branch

A merge commit has two parent commits

In Git, branching is very light weight





**Remote Repositories \& Branches**: In Git, remote repositories allow teams to collaborate.A remote is another copy of the repo on a server. Remote-tracking branches reflect the state of remote branches at last fetch/pull.

git fetch <remote>: download new commits from remote (does not merge)\[65].

git pull <remote> <branch>: fetch and then merge (or rebase) into your current branch

git push <remote> <branch>: upload your new commits on a branch to the server

conflicting changes rejected until you merge/rebase their work.



**Centralized Workflow**: single central repo, push to the main branch, conflicts are resolved as they arise. Simple but doesn’t scale well to very large teams.



**Integration-Manager Workflow**: Common in open-source fork the main repository, push changes to their fork, submit pull requests or merge requests to an integrator, integration manager (project maintainer) reviews and merges changes into the official repo



**Dictator-and-Lieutenants Workflow**: Used by very large projects, There is a project lead and trusted lieutenants,Developers work on topic branches, s, frequently rebase their work on the latest master (to keep history linear), This hierarchical model helps manage extremely large contributions, Rebasing avoids too many merge commits



**Handling Multiple Contributors**:

Frequent integration: Don’t let branches drift too far apart

Consistent workflow guidelines

Commit access control: only maintainers can push to main, Others must contribute via forks and pull requests



**Commit Guidelines**: Write descriptive commit messages, Make logical commits(each address one issue/feature), Use code review,  Check like whitespace errors



**Repository Hosting \& Team Management**:

Pull Requests/Merge Requests: review code, discuss, and approve before merging,

Issue Tracking

Continuous Integration hooks

Organizations and Teams: an organization can own repositories and manage members’ access rights



**Continuous Collaboration Issues**: “throw it over the wall”, Good version control practices + team culture mitigates these issues.



##### Week4:

**Tips**:

four main Configuration Management (CM) activities are System building, Version management, Change management, Release management

main inputs to an automated build system are Source code, configuration files, data files, libraries, and compilers 

increment the MAJOR version when make incompatible API changes

In Makefile, start a command with ( \\t )

Patch release: Bug fixed, minor changes 1.0.1

Minor release: New features 1.1.0

Major release: Changes break backward 2.0.0

In Makefile, a variable MYVAR is denoted as $(MYVAR)





**Software Configuration Management (SCM)**:Build Automation ensures that building the system, repeatable and reliable with minimal human effort



**Why Build Automation**:

Consistency: consistent results

Efficiency: Saves developer time and reduces mistakes

Continuous Integration: every commit can trigger an automated build/test

Complexity management:Build tools handle these systematically.



**Make and Makefiles**: Make is one of the oldest build tools, Makefile to define targets, dependencies, and commands

is timestamp-based: rebuilds targets, have newer timestamps. Key features: macros (variables), pattern rules, special targets

Makefile rule Student.java into Student.class: Student.class: Student.java

recipe for a target will be executed if One of the dependencies is newer than the target



**Apache Ant**: uses XML files, define targets and tasks in XML, Ant compiles Java source to classes/ directory, then packages a JAR

**Advantage**: can script any sequence of steps; not limited to file timestamps. Good for complex tasks.

**Disadvantage**: Verbose XML, no standard structure, Maintaining large Ant scripts can become cumbersome.



**Apache Maven**: “convention over configuration.” ,  Maven defines a standard project structure and lifecycle,  uses a Project Object Model (POM) file, source code is in src/main/java, tests in src/test/java, outputs go to target/

**key features**:

Lifecycle phases: Running mvn package will automatically compile sources, run tests, then package the code

Dependency Management: Maven can automatically download project dependencies from a central repository

Plugins:: Maven’s functionality is extended via plugins

Advantage: Standardization has a similar structure and build commands, Less verbose

Disadvantage: The rigid structure may not fit all projects, XML can still be verbose



**Gradle**: newer build tool that combines the flexibility of Ant with the conventions of Maven, a Groovy (or Kotlin) DSL instead of XML, highly customizable and supports incremental builds, organized into tasks, (forming a DAG – Directed Acyclic Graph, Gradle embraces convention (especially if using Gradle Wrapper and standard plugins for Java, etc.), via code



**SCM Concepts in Build**:

configuration management concepts:

**Codelines and Baselines**: A codeline is a sequence of versions of source code (like a branch), A baseline is a stable snapshot (a labeled/released version) that serves as a reference point

Semantic Versioning: : Convention of version

numbers MAJOR.MINOR.PATCH (Major changes break compatibility, Minor add features but backwards compatible, Patch are bug fixes

Release Management: preparing software for release (packaging, release notes, version tagging)tracking, versions deployed to customers



##### Week5:

Testing is the primary method of software verification(meets requirements and is defect-free)

**Why Testing Matters**:n cause huge financial loss, endanger lives, improves quality, catching defects before deployment, reduces risk

**Testing Fundamentals**: Who: Developers (unit tests), dedicated QA/testers, end-users (acceptance/beta testing). When: In waterfall, testing is a distinct late phase, ; in agile, testing is continuous, and automated tests run frequently

**Testing Levels**: 

Unit Testing: Verify individual components, Usually done by developers

Integration Testing: Verify interactions between integrated units/modules

System Testing: complete integrated system against requirements(System works as a whole)

Acceptance Testing: performed with customer involvement

Regression Testing: Re-running test suites after changes to ensure no new bugs

alpha/beta testing: (alpha – internal, beta – external users)



**Testing Techniques**:

Black-Box Testing: without seeing the code. Focus on input-output behaviour for a function defined by a spec, create tests for each requirement,  Equivalence partitioningand boundary value analysis

White-Box Testing: knowledge of internal code structure, tests to exercise all branches of a decision, loops, or specific paths, Coverage criteria



**Test-Driven Development (TDD)**: : An agile testing practice, written before the code, Red – write a small test and see it fail; Green – write just enough, Refactor – improve code while keeping tests green. TDD yields a comprehensive suite



**Test Case Design**:

Equivalence Classes: program should behave similarly

Boundary Values: reveal off-by-one errors

Error Guessing/Guidelines: : Leverage experience or common bug patterns



**Test Automation Goals**: Improve quality by catching bugs early (every code change triggers tests). Serve as executable 

specifications(readable, describe behaviour)

Prevent regressions: a bug is found, a test is added

Localize defects: a failing test pinpoints the problematic component

Be easy to run: one command to run all tests, ideally fast

Minimize maintenance cost: tests should be reliable



**Testing Patterns and Smells**:test design patterns and test design patterns(common problems in test code)





