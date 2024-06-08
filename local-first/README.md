# Local First

- Hosted by [Robert Hostlowsky](https://github.com/jscraftcamp/website/blob/main/participants/robert-hostlowsky.json)

## Entry point

- Web: [https://localfirstweb.dev/](https://localfirstweb.dev/)
  - Lots of resources to get started, _"Things to read"_ & _"Things to watch"_
- There was a conference recently, find it here [Local First Conf](https://www.localfirstconf.com/)

## What is Local First?

There was a discussion about the meaning of local first and no agreement.
Two completely different versions of "local first" where announced:

1. **Privacy driven** (i.e. local ONLY).
   You don't want that your data is hosted by a third party, so it never leaves your machine.
   The server is only used to distribute the application.
2. **Accesibility driven** (i.e. local FIRST).
   You don't want to depend on a remote server to use your data.
   The data is stored locally, but you also may put it into a server for syncing purposes.

## Local First, in general

- We want to store that in our local machine
  - Think a to-do list. Why do I need the items in the server?
- Local Storage would be an example solution of "local first"
- **You still have a server!!!** It's just the data which is not there
  - You don't sync using a server
  - **Syncing** is, unsurprisingly, a problem (see below)

### How's that different from a desktop application?

- "We want to use a server to distribute the application and it works in the browser"
- But in purity, a desktop application can be part of the Local First movement

### Syncing

- Multiple solutions suggested, e.g. [Replicache](https://replicache.dev/)
- The docs in the Local First website go very in depth about this topic.

## Why would I want to develop "local first"?

- Save costs of extra servers
- Better accessibility of your application (e.g. offline mode)
- Better performance (no network latency)
- Avoid problems with GDPR
  - For example: even if you are hosting your data in AWS Frankfurt, the US goverment may ask AWS for the data.
    If AWS complies, then YOU as the owner of the data, can be made SUED -- i.e. a punishment by the data protection authority.
    This is all regulated by the European GDPR.
  - Possible solutions
    1. Technical (e.g. end to end encryption)
    2. Use an european provider

## Related

- [Offline First](https://offlinefirst.org/)
