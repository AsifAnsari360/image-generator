## Elastic Load Balancing (ELB)

**Elastic Load Balancing** automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances.

- Acts as a single point of contact for all incoming web traffic to your Auto Scaling group.
- As you add or remove EC2 instances, the ELB routes requests across all resources, balancing the workload.
- Ensures no single instance is overwhelmed, improving fault tolerance and availability.

**Elastic Load Balancing** and **EC2 Auto Scaling** work together to maintain application performance and availability.

![Image](https://github.com/user-attachments/assets/10d4df29-01cf-488a-9c55-9df6a05def49)

![Image](https://github.com/user-attachments/assets/f5727ba6-f94f-485e-b30e-a4ee5a64dab7)

---

## Messaging and Queuing

In microservices and distributed architectures, reliable communication between components is crucial. AWS provides two core services for messaging and queuing:

![Image](https://github.com/user-attachments/assets/632d6894-5639-41d4-916c-eee20819e841)

![Image](https://github.com/user-attachments/assets/ff33c4c6-b4d6-463b-9373-4c2cf7d02344)

### Amazon Simple Notification Service (SNS)

- **Amazon SNS** is a flexible publish/subscribe (pub/sub) messaging service.
- Publishers send messages to "topics." Subscribers receive those messages.
- Subscribers can be HTTP endpoints, email addresses, AWS Lambda functions, and more.
- Example: Like a coffee shop cashier passing orders (messages) to a barista (subscriber).

### Amazon Simple Queue Service (SQS)

- **Amazon SQS** is a fully managed message queuing service.
- Decouples sending, storing, and receiving messages between software components.
- An application sends messages to a queue; another retrieves, processes, and deletes them.
- Prevents message loss and enables fault-tolerant processing.

---

## Serverless Computing

Traditionally, running applications on EC2 involves provisioning instances, uploading your code, and managing the infrastructure:

1. Provision instances (virtual servers).
2. Upload your code.
3. Continue to manage the instances while your application runs.

![Image](https://github.com/user-attachments/assets/3605eaf5-6393-46a8-9353-d3e01aa5c264)

### AWS Lambda

- **AWS Lambda** enables you to run code without provisioning or managing servers.
- Pay only for compute time consumed; billing is metered in milliseconds.
- Upload your code, define an event source (trigger), and Lambda runs your code automatically when triggered.
- Example use case: Automatically resize images when uploaded to the cloud.

![Image](https://github.com/user-attachments/assets/60f85a62-c641-4d8e-a6ab-09e9ebb2861a)

**Lambda Steps:**
1. Upload your code to Lambda.
2. Set your code to trigger from event sources (other AWS services, HTTP endpoints, mobile apps, etc.).
3. Lambda runs your code only when triggered.
4. Pay only for the compute time when code executes.

---

## Containers

Containers provide a standard way to package your application's code and dependencies into a single object. Containers are ideal for secure, reliable, and scalable application deployments.

![Image](https://github.com/user-attachments/assets/05084129-a602-4425-a477-15fccddde766)

![Image](https://github.com/user-attachments/assets/845bcc3e-8ff9-4c94-bdbc-4695d335747b)

### Amazon Elastic Container Service (ECS)

- **Amazon ECS** is a highly scalable and high-performance container management service.
- Supports Docker containers (build, test, deploy apps quickly).
- Use API calls to launch and stop Docker-enabled applications.

### Amazon Elastic Kubernetes Service (EKS)

- **Amazon EKS** is a fully managed Kubernetes service for running containers at scale.
- Kubernetes is open-source software for deploying and managing containerized applications.
- AWS works closely with the Kubernetes community, ensuring easy adoption of new features.

### AWS Fargate

- **AWS Fargate** is a serverless compute engine for containers.
- Works with both ECS and EKS.
- You do not provision or manage any servers; simply specify and run your containers.
- AWS Fargate manages all server infrastructure, and you only pay for resources your containers use.

---

## Summary

- **Amazon EC2 Auto Scaling**: Automatically adjust EC2 resources based on demand to optimize cost and performance.
- **Elastic Load Balancing**: Automatically distribute incoming traffic to maintain healthy, balanced workloads.
- **Amazon SNS & SQS**: Decouple microservices and distributed systems using messaging and queues.
- **AWS Lambda**: Run code without servers; pay only for execution time.
- **Containers (ECS, EKS, Fargate)**: Run and scale containerized applications with or without managing underlying servers.

---

**For more information, visit:**
- [Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)
- [Elastic Load Balancing](https://aws.amazon.com/elasticloadbalancing/)
- [Amazon SNS](https://aws.amazon.com/sns/)
- [Amazon SQS](https://aws.amazon.com/sqs/)
- [AWS Lambda](https://aws.amazon.com/lambda/)
- [Amazon ECS](https://aws.amazon.com/ecs/)
- [Amazon EKS](https://aws.amazon.com/eks/)
- [AWS Fargate](https://aws.amazon.com/fargate/)
