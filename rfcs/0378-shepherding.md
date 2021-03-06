- Feature Name: shepherding
- Start Date: 2019-09-10
- RFC PR: https://github.com/rust-embedded/wg/pull/378
- Rust Issue: (leave this empty)

# Summary
[summary]: #summary

In order to keep progress moving in the Embedded WG, this RFC proposes adopting the "Shepherding" method for tracking potential and in-progress project worked on by members of the Rust Embedded community.

Projects tracked by the Shepherding process are intended to be larger scale works, with a fixed "end goal", that can be achieved by a group of people, and are not blocked by outside factors, such as changes to the upstream Rust or LLVM projects, unless the project scope includes these changes.

# Motivation
[motivation]: #motivation

In 2018, the Embedded WG came together to get embedded development in Rust to a stable level. Following the success of this venture progress has continued, but due to a lack of concrete items to focus on, and a lack of free time to work on specific items, 2019 has had less focus.

Additionally, we hope to provide more direct routes for individuals in the community to contribute to improving the Embedded Rust ecosystem, as well as provide necessary mentoring and support.

This RFC proposes a structure for proposing, selecting, and tracking progress on larger scale improvements to the Embedded Rust ecosystem.

For a general background on the concept of Shepherding, refer to the blog posts by [James Munns] and [Niko Matsakis].

[James Munns]: https://jamesmunns.com/blog/shepherding-3-1/
[Niko Matsakis]: http://smallcultfollowing.com/babysteps/blog/2019/09/11/aic-shepherds-3-0/

# Detailed design
[design]: #detailed-design

This RFC covers four main stages of how we tackle large scale work, referred to as "focus projects": **Proposal**, **Selection**, and **Tracking**, and **Completion**.

## Proposal

Anyone may propose a large scale project to be worked on. Projects are proposed by opening an PR that copies the project template from `0000-project-template.md` to `projects/in-progress/0000-your-project-name.md`.

All proposals should contain the following information in the template file:

1. What is the current problem/shortcoming?
2. What is the relevance to the Rust Embedded Ecosystem?
3. What is the desired outcome to address this problem/shortcoming?
4. What is necessary to achieve this outcome?

After opening this issue, the proposer of this project should solicit feedback from Working Group members to refine the proposal, and the steps necessary to address this. Once the proposal has been refined, the proposer should find a member of the working group to **shepherd** the issue.

Once a potential shepherd has been found, the project may be selected.

## Selection

A project does not require full WG approval to be selected, only the sponsorship of one or more WG members. This member will be expected to provide status updates at the weekly Matrix meeting on the status of this project. If the WG member is unable to attend, they can delegate this responsibility as necessary.

A project moves to the tracking state once the PR adding the project to the `projects/` folder has been approved by the shepherding WG member.

It is recommended (but not a hard rule) that a WG member shepherds no more than one project at a time, to limit the number of in-flight projects at once.

## Tracking

Each week, the shepherd of each in-progress project should be prepared to give a short update in the Matrix meeting on the status of their project, and solicit help if additional assistance is needed.

Priority in each meeting will be given to discuss projects, if there are no critical issues to discuss (upcoming breakages, etc).

Updates will be expected until a project moves into a completion state.

If any major changes are made to the goals of the project, or if the WG shepherd changes, the status should be updated in the markdown file in `projects/`. This file does not need to be updated for regular status items, and should instead be tracked in an external repository linked in this file.

## Completion

There are three main ways a project can be completed: **Finished**, **On-Hold**, or **Rejected**.

Once a project has been completed, the WG shepherd is no longer required to provide regular status updates.

### Finished

If the work has completed successfully by meeting the current or revised goals, and does not require ongoing focus, this can be signified by submitting a PR to move the project file from `projects/in-progress/` to `projects/completed/`. This move only requires the approval of the shepherding WG member.

It is recommended to add a section to the project file summarizing the outcome of the project, and what was achieved.

### On-Hold

If the work need to be put on hold due to availability or technical reasons, this can be signified by submitting a PR to move the project file from `projects/in-progress/` to `projects/on-hold/`. This move only requires the approval of the shepherding WG member.

If a project is not expected to make progress, or hasn't made progress, for one month or more it is recommended that it be moved to the on-hold state.

When moving a project to the on-hold state, a section should be added to the project file describing what this project needs to resume work (e.g. a new shepherd, people to work on it).

An on-hold project can be moved back into in-progress with a PR and approval from a WG shepherd. At this point, status updates are expected to resume.

### Rejected

If a project no longer makes sense, or has been in the on-hold state for a significant time period, a project can be moved the Rejected state by moving the project file to `projects/rejected`. This move can be signified with a PR, and only requires the approval of the shepherding WG member.

Rejected projects can still be moved back into in-progress if necessary, though the rejected state signifies that progress is unlikely to change unless a significant event happens (a technical shortcoming is overcome, or new people are available to work on this project).

It is recommended to add a section to the project file summarizing why a project was rejected, and what items would need to be addressed to re-open this project in the future.


# How We Teach This
[how-we-teach-this]: #how-we-teach-this

## Vocabulary

**Project file** - This is a markdown document that contains core information about each project. It lives within the `project/` folder, and may move into subfolders to signify the project state.

**Working Group Shepherd** - This is a member of the working group who is responsible for providing status updates, making sure a project is continuing, and providing mentorship to people working on the project. Work is generally **NOT** performed only by the shepherd, and the expectation is that multiple people will work on any given project.

# Drawbacks
[drawbacks]: #drawbacks

This requires some administration overhead, and is a new concept to track in addition to the RFC process.

# Alternatives
[alternatives]: #alternatives

* Periodic goal meetings
* Top down decisions and assignment of tasks

# Unresolved questions
[unresolved]: #unresolved-questions

None known at this time
