# Minecraft Server on AWS

This project sets up a Minecraft server on an Amazon EC2 instance using AWS CloudFormation.

## Overview

The CloudFormation template in this project sets up the following resources:

- A VPC (Virtual Private Cloud) for hosting the Minecraft server.
- A public subnet within the VPC.
- An internet gateway attached to the VPC for internet access.
- A route table and a route that directs all traffic to the internet gateway.
- An IAM role and instance profile for allowing the EC2 instance to communicate with AWS Systems Manager.
- A security group that allows incoming TCP traffic on port 25565 for Minecraft.
- An Elastic IP address for the EC2 instance.
- An EC2 instance that runs the Minecraft server. The instance is of type `t4g.small` and uses the latest Amazon Linux AMI.

## Parameters

The template takes the following parameters:

- `MinecraftServerUrl`: The URL to download the Minecraft server jar file.
- `JavaXmxValue`: The maximum memory allocation pool for the JVM.
- `JavaXmsValue`: The initial memory allocation pool for the JVM.
- `LatestAmiId`: The ID of the latest Amazon Linux AMI.

## Outputs

The template outputs the following:

- `MyEC2Instance`: The ID of the EC2 instance running the Minecraft server.
- `MyEIP`: The Elastic IP address of the Minecraft server.

## Usage

To use this template, navigate to the AWS CloudFormation console and create a new stack. Upload the template file and provide the necessary parameters. Once the stack creation is complete, you can connect to the Minecraft server using the outputted Elastic IP address.

### Sources:

I used following blog posts as a reference for this:
https://aws.amazon.com/blogs/gametech/setting-up-a-minecraft-java-server-on-amazon-ec2/

Made with ❤️ by Luke