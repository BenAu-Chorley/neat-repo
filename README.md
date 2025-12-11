## README for a neat repo
This repo is just a demo of a fictitious project showcasing how neat commit history could help future development / reviews

## Why branching
- a core function of distributed coding
- allows a team full-throttled in parallel
- spreading responsibilities over team members among all projects / repos
- improve collaboration and facilitate code review on changes
- localize knowledge transfer to each change

## An example of agile methodology - using JIRA + github
- using a JIRA story to link up with a branch of code changes
- background of story and requirements well explained in that JIRA story
- agile team well briefed on the JIRA story requirements at the start of sprint
- each team member picked up one story at a time and create a feature branch from master
- once a feature change is ready for code review, that implementer creates a pull request
- another team member volunteers / be invited to review the changes in the pull request
	- so each time a code review is very localized to the specific changes involved and no more
- once reviewer approves, the implementer rebase and squash a branch chain into a single node before making a merge commit into the master branch
- other implementers would find their branch originates from an obsolete node at this point. He/she needs to rebase from master and resolve any conflicts before a pull request
- the process repeats
- all this to all projects and the team will become very resilient
- BAs / users can keep track of the progress of changes in JIRA
- breaking down changes into very small pieces and we'll get a very agile and responsive team
- sidenote: git can be used offline so most of the time we don't rely on the presence of github while we build

## Example: relatively message merge history
- [https://github.com/FerAnimaciones/TikTok-Code/network](https://github.com/FerAnimaciones/TikTok-Code/network)
- [https://github.com/githubError/MessyRepository/network](https://github.com/githubError/MessyRepository/network)
- It's hard to tell from where a change was introduced

## Example: the advantage of a neat merge history
- [https://github.com/BenAu-Chorley/neat-repo/network](https://github.com/BenAu-Chorley/neat-repo/network)
- very easy to tell when a feature / fix was introduced
- changes are ordered sequentially while dev works carried out in parallel

## Example sequence of event

### step 1 - JIRA ticket "work-5" was picked up by dev1
- commits keep piling up while building (2 commits already). That's ok, keep going

### step 2 - An urgent fix comes in, dev2 picks up
- branch out from latest master. New branch is called "urgent-fix"

### step 3 - demo of creating pull request
- dev2 squashes / rebases "urgent-fix"
- create a pull request on "urgent-fix"
- dev2 ask for a reviewed by dev3 and approved the PR
- dev3 approved
- dev2 merge "urgent-fix" to master
- dev2 deploy the latest master
- dev2 delete both the local and the remote "urgent-fix" branch

### step 4 - demo of resolving conflict on branch "work-5"
- now the node "work-5" stemmed from became obsolete because of "urgent-fix"
- dev1 needs to rebase it's local work on the latest remote master
- dev1 resolves all conflicts locally, but now the history of branch "work-5" has diverged from the remote
- dev1 needs to force push the "work-5" branch to make remote "work-5" on the same page
- dev1 goes on building "work-5"
- feature dev work completes, code changes on "work-5" is ready for review
- dev1 squash / rebase his code changes in "work-5" and force push first before creating a PR
- PR is reviewed and approved by dev2
- dev1 merges "work-5" to master. Now dev1 deploys master to production
- dev1 deletes the local and remote "work-5" branch afterwards

