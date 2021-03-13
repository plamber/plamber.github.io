---
layout: post
title:  "Who are the key stakeholders of the CLI for Microsoft 365?"
author: plamber
categories: [ Development, GitHub, CLI ]
tags: [CLI]
featured: true
---
The [CLI for Microsoft 365](https://github.com/pnp/cli-microsoft365) is a cross-platform command-line interface used to manage or automate Microsoft 365 resources. It is a PnP and community-driven initiative that is growing rapidly over time. Every project has key stakeholders that approach the CLI in different ways.

### The CLI customer
The CLI is targeting developers and IT-Pros to automate Microsoft 365 related processes. If you are like me, all repetitive tasks are automated with some sorts of scripts (I call it the non-repetition-syndrome).

The usage scenarios range from provisioning resources using CI/CD pipelines, creation of reporting scripts or performing day-to-day activities in the Microsoft 365 ecosystem. Third-party projects might use and integrate the CLI in their codebase as it is done for [Doctor](https://github.com/estruyf/doctor).

These persons get started using the official [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) documentation finding useful information on how to install the CLI and use the CLI. There is also a growing [sample scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/) section showing how you could create your first scripts with the CLI using different shells.

## The CLI contributor
Being a customer does not mean that you might not be able to actively contribute to the CLI. There are many different ways how you could make your contribution:

### Spread the love
Talk to your colleagues at work, use socials (#CLIMicrosoft365), or make a presentation about your lessons learned at user groups or conferences. Sharing is caring.

### Do you have an idea of how to improve the CLI? Have you found a bug?
The CLI and its community grow with the contributions provided by everyone. Let the community and the project know if you have interesting use-cases you want to tackle or even issues that stop you from using the CLI. The project can only improve if it gets proper feedback from everyone interested in the CLI. Things that do not work at all or very well today might be solved tomorrow with your valuable feedback.

Have you seen some interesting code samples in Microsoft 365 that you do not know how to solve in the CLI? Create a *new sample script* issue [here](https://github.com/pnp/cli-microsoft365/issues) and let the community know. You might find somebody in the community interested to pick it up and create the sample.

Get your free GitHub account (don't tell me you don't have one yet) and start a [discussion](https://github.com/pnp/cli-microsoft365/discussions) or create an issue (bug report, enhancement, sample scripts) in the [issues](https://github.com/pnp/cli-microsoft365/issues) section.

### Do you want to create samples or write your first command?
As you might have guessed everything starts with a GitHub issue that is triggering an enhancement activity for the CLI. First of all, an issue must be tracked. The maintainers of the CLI project will then help you classify the issue and narrow down the discussion to have a clear idea of what is going to be done.

Afterward, you or somebody from the community can pick this topic up by being assigned to the issue. This means that this person is actively working on this problem.

This person can follow the [contributing guides](https://github.com/pnp/cli-microsoft365/wiki) explaining how to set up the development environment and creating the first contribution. Once the contribution is ready to be shared the changes to the project are pushed to the original CLI project by submitting a pull request [PR](https://github.com/pnp/cli-microsoft365/pulls).

This is the moment where a project maintainer will pick up your pull request and verify that it works as expected. Some PRs might be more complex and require some feedback-loops before being submitted to the codebase.

## The CLI maintainer
If you are an active contributor for a longer period of time you might be asked to take up the role of project maintainer. Being a maintainer does not mean that you have to write more samples or commands. I learned that being a maintainer is more about community engagement and ensuring that the project is kept alive. 

The maintainer is a CLI customer and contributor at the same time and keeps the community together. With a good running community, the project will grow in usage and quality. A maintainer might be required to follow these additional activities:
- Track discussions, issues, and PRs and ensure these are classified and assigned properly. Kind of project manager/scrum master of the project.
- Validate the incoming pull requests and merge the changes to the code base
- Engage the community and grow the community 

## Summary
There are different stakeholders in a project like the CLI for Microsoft 365 that are actively engaged in what we call community. It does not matter if you take up one or multiple roles. The most important thing is that everyone with a small or bigger contribution helps this project to grow and others to tackle everyday problems. 


Sharing is caring.