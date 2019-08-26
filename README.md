# Near Real-Time Data: The Beauty of Pub/Sub Systems and Getting Started with Kafka
## RE-WORK, AI In Insurance Summit @ NYC

For the Hands-on Kafka portion of the Kafka Workshop, it will be supremely helpful to have the following installed ahead of time. (Full disclosure: I do not own a Windows machine, so I cannot guarantee that I'll be able to provide competent technical support for Windows-related issues)

### Java (most important)

Check to see if you already have Java installed. In Terminal (or Windows equivalent, such as Bash), try:

`java --version`

If you see something other than an error message, you should be all set.
Otherwise, please continue to:

https://www.oracle.com/technetwork/java/javase/downloads/jdk12-downloads-5295953.html

Toward the bottom, for "Java SE Development Kit 12.0.2", select the "Accept License Agreement" radio button, and click to download the OS version that is appropriate for you (macOS or Windows).

After downloading, find it in your Downloads folder, and open. Walk through the installation wizard.

Check that installation completed succesfully by opening a Terminal (or Bash, etc.) window and typing:
`java --version`

You should see something like:
```
java 12.0.2 2019-07-16
Java(TM) SE Runtime Environment (build 12.0.2+10)
Java HotSpot(TM) 64-Bit Server VM (build 12.0.2+10, mixed mode, sharing)
```

or similar.

## Apache Kafka

Follow "Step 1: Download the code" provided here: https://kafka.apache.org/quickstart

And that's it. We'll walk from Step 2 to Step 5 together as a class, and we'll demonstrate the importance of certain configuration settings, and how changing them will impact your Kafka implementation.
