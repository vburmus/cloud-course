# Volodymyr Burmus - Cognito TicTacToe report

- Course: *Cloud programming*
- Group: PN 11.15
- Date: 08.06

## Environment architecture
![img.png](imgs/img.png)
- The architecture consists of the following components:
  - S3 bucket: Used to store the frontend code and assets.
  - RDS instance: Used to store the game state in the game table.
  - Lambda function: Used to handle the game logic and send messages to the SNS topic.
  - SNS topic: Used to send messages to the frontend.
  - VPC Endpoint: Used to allow access to the SNS service from Lambda.
  - Security Group: Used to allow access to the RDS instance from the backend and allow additional traffic to Lambda on 443.
## Preview
 - RDS is used to store the game state. The game state is stored in the game table from backend.
![img_1.png](imgs/img_1.png)
 - Security group is used to allow access to the RDS instance from the backend and allow additional traffic to lambda on 443.
![img_2.png](imgs/img_2.png)
 - VPC Endpoint is used to allow access to the SNS service from Lambda.
![img_3.png](imgs/img_3.png)
 - Lambda code is used to handle the game logic and to send messages to the SNS topic.
![img_4.png](imgs/img_4.png)
 - Lambda configuration
![img_5.png](imgs/img_5.png)
![img_6.png](imgs/img_6.png)
![img_7.png](imgs/img_7.png)
 - SNS topic is used to send messages to the frontend.
![img.png](imgs/img_8.png)
## Reflections

- What did you learn?
  -  I learned how to configure and deploy various AWS services using Terraform, including S3, RDS, Lambda, API Gateway, and SNS.
  - I gained experience in setting up network configurations such as security groups, VPC endpoints, and configuring access controls for 
     different AWS services.
  - I learned how to integrate different AWS services to build a complete application architecture.
- What obstacles did you overcome?
  - I faced challenges in configuring S3 with Terraform due to deprecated functions and IAM policy restrictions. However, I was able to overcome these challenges by researching and finding alternative solutions.
  - Setting up the RDS instance with Hibernate and configuring Lambda to interact with both RDS and SNS simultaneously was also challenging. I had to troubleshoot issues with Python imports and Lambda layer configuration, but eventually, I resolved them by using VPC endpoints.
  - Issues with Python imports and layer configurations when integrating Lambda with SNS
  - Configuring Endpoints for SNS to reach in from VPC
- What did you help most in overcoming obstacles?
    - Researching AWS documentation, online resources, and community forums helped me understand the best practices and solutions for 
      configuring AWS services with Terraform.
    - Experimenting with different configurations and testing each component individually helped me identify and resolve issues effectively.
- Was that something that surprised you?
  - Firstly, I was surprised by the complexity of integrating multiple AWS services with Terraform and configuring network settings on Lab 
Account to ensure secure and efficient communication between services. I also found it challenging to troubleshoot issues with Python 
imports and Lambda configurations, but I was able to overcome these challenges through persistence and experimentation.
  - Also, I was surprised by the limitations of Terraform in managing certain AWS services, such as S3, due to deprecated functions and IAM 
    policy restrictions. However, I was able to find alternative solutions and workarounds to address these limitations.
  - Moreover, I was surprised by the importance of setting up VPC endpoints for SNS to allow Lambda to send messages to the SNS topic 
    securely. This configuration was crucial for ensuring that the application architecture was secure and efficient.
  - Finally, I was surprised by the power and flexibility of AWS services and how they can be integrated to build complex and scalable 
    applications. I gained a deeper understanding of how different AWS services work together and how they can be used to create robust and reliable applications.