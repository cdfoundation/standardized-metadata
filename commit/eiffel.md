In the Eiffel event protocol, a commit is identified by an [EiffelSourceChangeCreatedEvent](https://github.com/eiffel-community/eiffel/blob/master/eiffel-vocabulary/EiffelSourceChangeCreatedEvent.md).

That event contains the following event specific data:
- *author* - an optional object describing e.g. the name, email address and id of the author of the commit
- *change* - an optional object describing the SCM change in generic (non-SCM specific) terms, with these sub-parameters
  - *tracker* - an optional string stating the name of the SCM system used for the change (for example Gerrit or GitHub)
  - *id* - an optional string identifying the change within the SCM system used
  - *details* - an optional string representing a URI pointing at further details about the change, normally being a link to the change in the SCM system used
  - *insertions* - an optional integer describing the number of insertions made in the change
  - *deletions* - an otional integer describing the number of deletions made in the change
  - *files* - an optional string representing a URI pointing at a list of files changed
- *gitIdentifier* - an optional object describing a Git commit, relevant only if the change uses Git as version-control system, with these sub parameters
  - *commitId* - a string representing the commit identity (Git hash) of the change
  - *branch* - an optional string representing the branch used for the change
  - *repoName* - an optional string representing the name of the Git repository containing the change
  - *repoUri* - an optional string representing a URI pointing at the repository containing the change
- *svnIdentifier* - an optional object describing an SVN commit, relevant only if the change uses Subversion as version-control system. See the Eiffel event link in the top of this document for more details on this object.
- *svnIdentifier* - an optional object describing an SVN commit, relevant only if the change uses Subversion as version-control system. See the Eiffel event link in the top of this document for more details on this object
- *ccCompositeIdentifier* - an optional object describing a Clearcase change, relevant only if the change uses Clearcase as version-control system. See the Eiffel event link in the top of this document for more details on this object
- *hgIdentifier* - an optional object describing a Mercurial change, relevant only if the change uses Mercurial as version-control system. See the Eiffel event link in the top of this document for more details on this object

Complementing the mentioned parameters are also for example the following link types:
- *BASE* - An optional string referencing a previously merged source change, previously notified using an EiffelSourceChangeSubmittedEvent
- *PREVIOUS_VERSION* - An optional link referencing the previous version of this source change, if applicable, previously notified using an EiffelSourceChangeCreatedEvent
- *RESOLVED_ISSUE* - An optional string referencing an issue that was solved within this source change, previously notified using an EiffelIssueDefinedEvent
For a more complete view on the link types supported in this event, see the Eiffel event link in the top of this document

Complementing the mentioned parameters are also the generic metadata available in all types of Eiffel events, for example:
- *id* - A unique identity (UUID) of this specific event
- *version* - A string representing the version of the specification used for this specific event
- *time* - An integer representing the time (UNIX Epoc time) when this event was issued
For a more complete view on the link types supported in this event, see the Eiffel event link in the top of this document

Related to this event that is sent when an artifact is created, are other events that could be sent after this and referencing this event, such as the following:
- [EiffelSourceChangeSubmittedEvent](https://github.com/eiffel-community/eiffel/blob/master/eiffel-vocabulary/EiffelSourceChangeSubmittedEvent.md) - intended to be sent when a source change has been submitted/merged to the intended branch in the SCM system
- [EiffelCompositionDefinedEvent](https://github.com/eiffel-community/eiffel/blob/master/eiffel-vocabulary/EiffelCompositionDefinedEvent.md) - intended to be sent for example when a source change is included in a composition/baseline in a downstream integration source code repository

For a more complete view on event types available to be sent and linked to this event are seen in the complete Eiffel vocabulary seen here: https://github.com/eiffel-community/eiffel#contents
