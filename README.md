# Scaling Amazon EC2

Scalability involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling out or in. As a result, you pay for only the resources you use. You don’t have to worry about a lack of computing capacity to meet your customers’ needs.

If you wanted the scaling process to happen automatically, which AWS service would you use? The AWS service that provides this functionality for Amazon EC2 instances is **Amazon EC2 Auto Scaling**.

---

## Amazon EC2 Auto Scaling

If you’ve tried to access a website that wouldn’t load and frequently timed out, the website might have received more requests than it was able to handle. This situation is similar to waiting in a long line at a coffee shop when there is only one barista present to take orders from customers.

![Image](https://github.com/user-attachments/assets/d209a4b7-0c91-4f41-bf9f-dea03b32b52f)
---

### Example: Amazon EC2 Auto Scaling

In the cloud, computing power is a programmatic resource, so you can take a more flexible approach to the issue of scaling. By adding Amazon EC2 Auto Scaling to an application, you can add new instances to the application when necessary and terminate them when no longer needed.

Suppose that you are preparing to launch an application on Amazon EC2 instances. When configuring the size of your Auto Scaling group, you might set the minimum number of Amazon EC2 instances at one. This means that at all times, there must be at least one Amazon EC2 instance running.

![Image](https://github.com/user-attachments/assets/1e7a1450-1edd-491a-b3ec-5b36886fd584)
---

## Key Benefits

- **Automatic Scalability:** Responds automatically to changes in demand by launching or terminating instances based on policies and schedules that you configure.
- **Cost Optimization:** You only pay for the resources you use; helps prevent over-provisioning and reduces costs.
- **Improved Availability:** Maintains application availability by ensuring the correct number of EC2 instances are running to meet your workload requirements.
- **Flexible Configuration:** Set minimum, maximum, and desired levels of instances in your Auto Scaling group.

---

## How It Works

1. **Define An Auto Scaling Group:**  
   Configure the group to include details such as instance launch template, minimum, maximum, and desired number of EC2 instances.

2. **Monitor Application Health:**  
   Amazon EC2 Auto Scaling monitors the health of running instances and replaces any that become unhealthy.

3. **Scale Out/In Automatically:**  
   - **Scale Out:** Increases the number of instances during higher demand periods (adds more “baristas”).
   - **Scale In:** Decreases the number of instances when demand drops (removes idle “baristas”), saving costs.

---

## Learn More

- [Amazon EC2 Auto Scaling Documentation](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)
- [AWS Well-Architected Framework - Performance Efficiency Pillar](https://docs.aws.amazon.com/wellarchitected/latest/performance-efficiency-pillar/performance-efficiency-pillar.html)

---
