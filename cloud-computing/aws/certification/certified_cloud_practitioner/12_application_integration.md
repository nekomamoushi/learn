# Application Integration

## Simple Queue Service (SQS)

- Oldest AWS offering (over 10 years old)
- Fully managed service, use to decouple applications
- Scales from 1 message per second to 10,000s per second
- Default retention of messages: 4 days, maximum of 14 days
- No limit to how many messages can be in the queue
- Messages are deleted after they’re read by consumers
- Low latency (<10 ms on publish and receive)
- Consumers share the work to read messages & scale horizontally

## Simple Notification Service (SNS)

- The “event publishers” only sends message to one SNS topic
- As many “event subscribers” as we want to listen to the SNS topic notifications
- Each subscriber to the topic will get all the messages
- Up to 10,000,000 subscriptions per topic, 100,000 topics limit
- SNS Subscribers can be:
  - HTTP / HTTPS (with delivery retries – how many times)
  - Emails, SMS messages, Mobile Notifications
  - SQS queues (fan-out pattern), Lambda Functions (write-your-own integration)

## Amazon MQ

- SQS, SNS are “cloud-native” services, and they’re using proprietary protocols from AWS.
- Traditional apps running from on-premise may use open protocols:
  - MQTT, AMQP, STOMP, Openwire, WSS
- When migrating to the cloud, instead of re-engineering the application to use SQS and SNS, we can use Amazon MQ
- Amazon MQ = managed Apache ActiveMQ
- Amazon MQ doesn’t “scale” as much as SQS / SNS
- Amazon MQ runs on a dedicated machine (not serverless)
- Amazon MQ has both queue feature (~SQS) and topic features (~SNS)

### Kinesis

- Real-time big data streaming
- Managed service to collect, process, and analyze real-time streaming data at any scale
