# OrderDataIngestionService
Simulate pulling “order data” from an external API (like SAP), process it in microservices, and handle failures using SQS, DLQ, and CloudWatch monitoring.

Tech Stack:

Producer: Node.js script that calls a mock API and pushes messages to AWS SQS.

Consumer: Lambda or containerized microservice that processes the messages.

DLQ: For failed messages after retries.

CloudWatch: For alarms (high queue depth, message age, DLQ activity).

Idempotency: Store processed message IDs in DynamoDB to avoid duplicates.
