# AWS Connectivity and Networking

This document provides an overview of core AWS networking concepts, key VPC components, connectivity options, security mechanisms, and global content delivery services. Useful for AWS Cloud Practitioner exam preparation.

---

## Amazon Virtual Private Cloud (Amazon VPC)

**Amazon VPC** enables you to provision an isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define, organized into **subnets**.

- **Subnet:** A segment of a VPC for grouping resources (e.g., EC2 instances) based on security or operational needs. Subnets can be public (internet-facing) or private (internal).

### Connectivity Options

- **Internet Gateway:**  
  - Connects your VPC to the internet, allowing public traffic to access your resources (like a doorway to a coffee shop).
![Image](https://github.com/user-attachments/assets/73cb53c2-cb5d-43d6-858d-8b0c4454f0ad)

- **Virtual Private Gateway:**  
  - Allows protected, encrypted internet traffic (via VPN) from approved networks (such as on-premises data centers) to access private resources in your VPC.
![Image](https://github.com/user-attachments/assets/1bd6972f-e814-43b6-9e7c-018f4c56881e)

- **AWS Direct Connect:**  
  - Establishes a dedicated, private connection from your data center to your VPC (like a private hallway), reducing costs and increasing bandwidth.
![Image](https://github.com/user-attachments/assets/357a735f-4bce-4a0f-b4a5-2fe831fe01ec)

---

## Subnet Security Controls

![Image](https://github.com/user-attachments/assets/173388f1-8ec7-43bd-b5bf-17e88da88709)

- **Network Access Control Lists (Network ACLs):**
  - Virtual firewalls at the subnet level. Perform stateless packet filtering—check each packet entering/exiting, but don’t remember past requests.
  - Analogy: Passport control at a border, checking travelers both in and out, always consulting the full rulebook.
![Image](https://github.com/user-attachments/assets/937386d3-82be-4a62-b7bb-eb660daea4a7)

- **Security Groups:**
  - Virtual firewalls at the resource level (e.g. EC2). Perform stateful packet filtering—allow return traffic automatically, remembering past requests from the instance.
  - Analogy: A doorman who remembers returning guests and lets them in without new questioning.
![Image](https://github.com/user-attachments/assets/98836a54-28e5-4b8e-9ac0-ab6b1063bb32)


| Feature             | Network ACLs (NACLs)      | Security Groups            |
|---------------------|--------------------------|----------------------------|
| Level               | Subnet                   | Instance                   |
| Stateful/Stateless  | Stateless                | Stateful                   |
| Applies to          | All resources in subnet  | Individual EC2 instances   |
| Evaluation          | All rules evaluated      | All rules evaluated together|

- **Custom Rules:** You can configure custom rules for both ACLs and security groups to allow or deny specific inbound/outbound traffic.

### Stateful
![Image](https://github.com/user-attachments/assets/65eacfe0-2c8a-4871-b078-cd1411c0a185)

### Stateless
![Image](https://github.com/user-attachments/assets/535beba9-1b46-45b9-b74a-449dd518232a)

---

## VPC Component Usage Recap

- **Private subnet:** Use to isolate sensitive resources, such as databases with personal information.
- **Virtual private gateway:** Establish a VPN between your VPC and an internal (on-premises) network.
- **Public subnet:** Use for customer-facing web servers or other resources that need internet access.
- **AWS Direct Connect:** Use for a dedicated, private, high-bandwidth connection from your datacenter to your AWS VPC.

![Image](https://github.com/user-attachments/assets/02157995-02de-43aa-8937-8f4b7dd48bf5)

---

## Global Networking

### Domain Name System (DNS) and Amazon Route 53

- **DNS (Domain Name System):**  
  - Translates human-friendly web addresses (e.g., example.com) to IP addresses computers use to connect. Think of DNS as the internet’s phonebook.

![Image](https://github.com/user-attachments/assets/814dbbbe-e680-4d3b-9e39-0c8f0c6ef3ee)

- **Amazon Route 53:**
  - AWS’s scalable DNS web service.
  - Routes user traffic to AWS resources (e.g., EC2 instances, ELB) or external infrastructure.
  - Manages domain name registration and DNS records in one place.

### Example: Content Delivery with Route 53 and CloudFront

![Image](https://github.com/user-attachments/assets/a806b054-b429-40a3-aed0-944b17723a81)

Suppose AnyCompany’s app runs on an EC2 Auto Scaling Group behind a Load Balancer:

1. A customer requests data from AnyCompany’s website.
2. Amazon Route 53 resolves the domain name to its IP address and returns it to the customer.
3. The request is directed to the nearest Amazon CloudFront edge location.
4. CloudFront ultimately connects to the Load Balancer, which routes the request to an available EC2 instance.

---

## Summary

- **Structuring and connecting to a VPC:** Use subnets, gateways, VPNs, and Direct Connect.
- **Securing VPC resources:** Employ network ACLs for subnet-level and security groups for instance-level firewalling.
- **Global content delivery:** Use Amazon Route 53 for DNS and Amazon CloudFront for fast, reliable user experiences worldwide.

---

### Further Reading

- [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/index.html)
- [AWS Direct Connect](https://aws.amazon.com/directconnect/)
- [Security Groups and NACLs](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html)
- [Amazon Route 53](https://aws.amazon.com/route53/)
- [Amazon CloudFront](https://aws.amazon.com/cloudfront/)
