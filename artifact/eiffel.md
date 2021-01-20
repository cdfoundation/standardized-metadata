In the Eiffel event protocol, an artifact is identified by an [EiffelArtifactCreatedEvent](https://github.com/eiffel-community/eiffel/blob/master/eiffel-vocabulary/EiffelArtifactCreatedEvent.md).

That event contains the following event specific data:
- *identity* - A mandatory [purl identity](https://github.com/package-url/purl-spec) string of the created artifact, containing the version of the artifact
- *name* - An optional string containing the name of the artifact
- *fileInformation* - An optional array of file names that the artifact contains, together with an optional array of tags associated with each file
- *buildCommand* - An optional string describing the build command used to build the artifact
- *requiresImplementation* - An optional enum string defining whether this artifact requires an implementing artifact (typically used for interfaces requiring a backend implementation)
- *implements* - An optional array of [purl identities](https://github.com/package-url/purl-spec) identifying entities that this artifact implements (typically used to identify interface artifacts implemented by this artifact)
- *dependsOn* - An optional array of [purl identity](https://github.com/package-url/purl-spec) strings representing artifacts that this artifact depends on

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
- [EiffelArtifactPublishedEvent](https://github.com/eiffel-community/eiffel/blob/master/eiffel-vocabulary/EiffelArtifactPublishedEvent.md) - intended to be sent when an artifact is published to an archive of some kind (such as for example Artifactory or Nexus)
- [EiffelCompositionDefinedEvent](https://github.com/eiffel-community/eiffel/blob/master/eiffel-vocabulary/EiffelCompositionDefinedEvent.md) - intended to be sent for example when an artifact is included in a composition/baseline in a downstream integration artifact
- [EiffelConfidenceLevelModifiedEvent](https://github.com/eiffel-community/eiffel/blob/master/eiffel-vocabulary/EiffelConfidenceLevelModifiedEvent.md) - intended to be sent when an artifact has reached a defined level of confidence/maturity, through for example a test activity

For a more complete view on event types available to be sent and linked to this event are seen in the complete Eiffel vocabulary seen here: https://github.com/eiffel-community/eiffel#contents
