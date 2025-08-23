<h1>Design a Secure VPC Architecture</h1>

The main goal of this project is to design a secure and highly available VPC architecture on AWS, for a new web application that is being released. To achieve this, I will make use of the following resources: 
Amazon Global Infrastructure, VPC, subnets, route tables, Internet Gateways, and NAT Gateways.

<img width="1118" height="538" alt="image" src="https://github.com/user-attachments/assets/ef30fa3b-1ba2-40b0-88ee-ec57d0ced72a" />

The application comprises a public-facing web component and a backend database. While the web component is accessible from the Internet, the database is only accessible within the VPC.

I have designed two public subnets, one in each AZ to ensure high availability for the NAT gateways of our application. I have designed 4 private subnets, two in each AZ to ensure high availability for the Application and Databases. 

In order to provide internet connectivity, I have ensured the public subnets have access to the Internet via an Internet Gateway. I have also implemented NAT Gateways in the public subnets to allow instances in the private subnets to access the Internet for updates and patches, without being directly accessible from the Internet.

I created sample routing tables for the public and private subnets, ensuring proper routing for Internet access and internal communication.

For security, the databases in the private subnets can only be accessed from the application servers in the private subnets.




