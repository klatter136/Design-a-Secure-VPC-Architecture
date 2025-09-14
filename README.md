<h1>Design a Secure VPC Architecture</h1>

<img width="1118" height="538" alt="image" src="https://github.com/user-attachments/assets/ef30fa3b-1ba2-40b0-88ee-ec57d0ced72a" />

This project focused on designing a secure, highly available VPC architecture for a new web application. The goal was to create a network layout that separates public-facing components from private resources while maintaining strong security and reliable connectivity.

I used AWS core networking services—VPC, subnets, route tables, Internet Gateways, and NAT Gateways—to build the foundation. The application consists of a public web tier and a backend database tier. The web tier needs to be reachable from the Internet, while the database tier must stay private inside the VPC.

To achieve high availability, I created two public subnets (one in each Availability Zone) for NAT Gateways and four private subnets (two in each AZ) for application and database servers. This design ensures redundancy and fault tolerance across zones.

The public subnets connect to the Internet through an Internet Gateway. NAT Gateways in the public subnets allow the private instances to download updates or reach external services securely—without exposing them directly to the Internet.

I also built routing tables for both public and private subnets. Public subnets route traffic to the Internet Gateway, while private subnets route external traffic through the NAT Gateways. This ensures proper isolation and controlled Internet access.

Finally, I restricted database access to only the application servers inside the private subnets. This enforces the principle of least privilege and strengthens security at the network layer.




