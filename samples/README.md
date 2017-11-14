# Dialogflow API Java examples

These samples demonstrate the use of the [Dialogflow API][dialogflow].

These samples show how to detect intents with text, audio, and streaming audio.

These samples show how to manage contexts, entities, entity types, and intents

[dialogflow]: https://dialogflow.com/docs/getting-started/basics
[google-cloud-java]: https://github.com/GoogleCloudPlatform/google-cloud-java

## Java Version

This sample requires you to have
[Java8](https://docs.oracle.com/javase/8/docs/technotes/guides/install/install_overview.html).

### Download Maven

To get started, [download][maven-download] and [install][maven-install] it.

[maven]: https://maven.apache.org
[maven-download]: https://maven.apache.org/download.cgi
[maven-install]: https://maven.apache.org/install.html

### Setup

* Create a project with the [Google Cloud Console][cloud-console], and enable
  the [Dialogflow API][dialogflow-api].
* [Set up][auth] authentication. For
    example, from the Cloud Console, create a service account,
    download its json credentials file, then set the appropriate environment
    variable:

    ```bash
    export GOOGLE_APPLICATION_CREDENTIALS=/path/to/your-project-credentials.json
    ```
* Set PROJECT_ID in pom.xml to your Google Cloud Project Id.

[cloud-console]: https://console.cloud.google.com
[dialogflow-api]: https://pantheon.corp.google.com/apis/library/dialogflow.googleapis.com
[auth]: https://cloud.google.com/docs/authentication/getting-started

## Run the sample

To build the sample, we use Maven.

```bash
mvn clean package
```

## Samples

### Context Management
DialogFlow API Context sample.

Lists contexts:
```
mvn exec:java -DContextManagementList
```
Create an entity type with the given display name:
```
mvn exec:java -DContextManagementCreate
```
Delete entity type with the given entity type name:
```
mvn exec:java -DContextManagementDelete
```

### Detect Intent Audio
DialogFlow API Detect Intent sample with audio files. Returns the result of detect intent with an
audio file as input.

```
mvn exec:java -DDetectIntentAudioBookARoom
```
```
mvn exec:java -DDetectIntentAudioMountainView
```
```
mvn exec:java -DDetectIntentAudioToday
```
```
mvn exec:java -DDetectIntentAudio230PM
```
```
mvn exec:java -DDetectIntentAudioHalfAnHour
```
```
mvn exec:java -DDetectIntentAudioTwoPeople
```

### Detect Intent Stream
DialogFlow API Detect Intent sample with audio files processes as an audio stream.

```
mvn exec:java -DDetectIntentStreamBookARoom
```
```
mvn exec:java -DDetectIntentStreamMountainView
```

### Detect Intent Texts
DialogFlow API Detect Intent sample with text inputs.

```
mvn exec:java -DDetectIntentText
```

### Entity Management
DialogFlow API Entity sample.

List entities
```
mvn exec:java -DEntityManagementList
```
Create an entity of the given entity type
```
mvn exec:java -DEntityManagementCreate
```
Delete entity with the given entity type and entity value
```
mvn exec:java -DEntityManagementDelete
```

### Entity Type Management
DialogFlow API EntityType sample.

List entity types
```
mvn exec:java -DEntityTypeManagementList
```
Create an entity type with the given display name
```
mvn exec:java -DEntityTypeManagementCreate
```
Delete entity type with the given entity type name

Example output from `mvn exec:java -DEntityTypeManagementCreate`:
"projects/java-docs-samples-testing/agent/entityTypes/86f57a32-483a-4818-b080-764dbcb31c6a"

ENTITY_TYPE_ID=86f57a32-483a-4818-b080-764dbcb31c6a

Use the outputted ENTITY_TYPE_ID from your `mvn exec:java -DEntityTypeManagementCreate` call
```
mvn exec:java -DEntityTypeManagementDelete  -Dexec.args='delete ENTITY_TYPE_ID
--projectId PROJECT_ID' 
```

### Intent Management
DialogFlow API Intent sample.

List intents
```
mvn exec:java -DIntentManagementList
```
Create an intent of the given intent type
```
mvn exec:java -DIntentManagementCreate
```
Delete intent with the given intent type and intent value

Example output from `mvn exec:java -DIntentManagementCreate`:
"Intent created: name:"projects/java-docs-samples-testing/agent/intents/5294c404-2516-47df-9a36-f0168ceca6f8""

INTENT_ID=5294c404-2516-47df-9a36-f0168ceca6f8

Use the outputted INTENT_ID from your `mvn exec:java -DIntentManagementCreate` call
```
mvn exec:java -DIntentManagementDelete -Dexec.args='delete INTENT_ID --projectId PROJECT_ID'
```

### Session Entity Type Management
DialogFlow API SessionEntityType sample.

List session entity types
```
mvn exec:java -DSessionEntityTypeManagementList
```
Create an entity type with the given display name
```
mvn exec:java -DSessionEntityTypeManagementCreate
```
Delete entity type with the given entity type name
```
mvn exec:java -DSessionEntityTypeManagementDelete
```