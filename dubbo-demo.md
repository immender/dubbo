# Dubbo Demo

This directory contains basic usages of Dubbo to help Dubbo developers for debugging and smoke test purpose. If you are looking for Dubbo samples for study purpose, you should look into [here](https://github.com/apache/dubbo-samples) where you will find comprehensive usages for how to use Dubbo in different scenarios with the different features.

## How To Build

To build all demo applications from the source code, simply step into '_dubbo-demo_' directory and use maven to build:

```bash
mvn clean package
```

After build completes, a couple of fat jars are generated under '_target_' directory under each module directories, for example: '_dubbo-demo-api-provider-${project.version}.jar_' can be found under the directory '_dubbo-demo/dubbo-demo-api/dubbo-demo-api-provider/target_'.

## How To Run

Since the generated artifacts are fat jars backed by spring boot maven plugin, they can be executed directly with '_java -jar_', and since multicast is used for service registration, a necessary system property '**-Djava.net.preferIPv4Stack=true**' is required in order to registry and discover the demo service properly.

Use '_dubbo-demo/dubbo-demo-api_' as an example, to start the provider '_dubbo-demo-api-provider_', execute the following command:

```bash
java -Djava.net.preferIPv4Stack=true -jar dubbo-demo-api-provider-${project.version}.jar
```

To run the consumer '_dubbo-demo-api-consumer_', execute the following command:

```bash
java -Djava.net.preferIPv4Stack=true -jar dubbo-demo-api-consumer-${project.version}.jar
```

