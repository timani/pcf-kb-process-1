Loggregator Handbook
===========

-   Version-controlled
-   Forkable
-   Continuously updated
-   [Written in markdown](https://sculpin.io/)

Loggregator is composed of:
* **Sources**: Logging agents that run on the Cloud Foundry components.
* **Metron**: Metron agents are co-located with sources. They collect logs and forward them to:
* **Doppler**: Responsible for gathering logs from the **Metron agents**, storing them in temporary buffers, and forwarding logs to 3rd party syslog drains.
* **Traffic Controller**: Handles client requests for logs. Gathers and collates messages from all Doppler servers, and provides external API and message translation (as needed for legacy APIs).

Source agents emit the logging data as [protocol-buffers](https://github.com/google/protobuf), and the data stays in that format throughout the system.

#### Runner VMs

![Loggregator Diagram](https://github.com/cloudfoundry/loggregator/blob/develop/docs/loggregator.png )

In a redundant CloudFoundry setup, Loggregator can be configured to survive zone failures. Log messages from non-affected zones will still make it to the end user.

### Cloud Controller VMs

On AWS, availability zones could be used as redundancy zones. The following is an example of a multi zone setup with two zones.

### Contributing

Read [CONTRIBUTING.md](<CONTRIBUTING.md>) for more details on contributing
documentation improvements.

