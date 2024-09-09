=== Manual Cloud-based Web Deployment ===


=== 6409682942 Anallena Libha ===


- Project Overview
    This project focuses on deploying a Strapi web application on the Amazon Web Services (AWS) Cloud platform. The aim is to leverage various tools and technologies, including Linux CLI, Git, and cloud technologies, as studied in the CS360 course.



In this project, I learned how to deploy Strapi on a cloud platform, specifically AWS. I gained experience in using various tools and technologies such as Linux CLI for server management, Git for version control, and AWS for cloud deployment.



- Strapi
    Strapi is an open-source headless Content Management System (CMS) that provides a powerful and flexible backend for managing content. 
    It allows developers to create custom APIs easily and manage content through a user-friendly admin panel. 

    There are many usecases such as:
        Headless CMS: Manage content for websites, applications, and other digital products.
        Custom API Creation: Build and manage APIs for various applications with ease.
        Content Management: Organize and handle content in a structured way through an admin interface.

    Here are components of Strapi:
        Admin Panel: A user interface for managing content and configurations.
        API: Automatically generated RESTful and GraphQL APIs for interacting with content.
        Content Types: Define and manage the structure of content within Strapi.
        Database: Stores content and application data.

    To installing and running Strapi locally:
        1. Install Node.js, npm, yarn.
        2. Create a Strapi Project: 
                npx create-strapi-app my-strapi-project --quickstart
        3. Navigate to Project Directory:
                cd my-project
        4. Start Running Strapi:
                npm run develop
        5. Start Strapi in Production Mode:
                npm run start
        6. Build your admin panel.
                npm run build
    Visit http://localhost:1337/admin to access the Strapi admin panel.


- .gitignore in Strapi
    The .gitignore file in Strapi is used to specify files and directories that should be excluded from version control. 
    This includes:
        node_modules/: Contains all installed dependencies.
        .env: Holds environment variables such as database credentials.
        build/: Generated build files that are not necessary to include in version control.
    This helps in keeping the repository clean and ensures sensitive information is not exposed.


- GitHub Repository Setup
    To Creating a GitHub Repository >>> Sign in to GitHub and go to the GitHub homepage. >>> Click on the "+" icon in the top right corner and select "New repository." >>> Name your repository (e.g., my-strapi-project) and add a description. >>> Choose the repository visibility (public or private) and initialize it with a README if desired. >>> Click "Create repository."


    code:
        cd my-project
        git init
        git remote add origin https://github.com/username/my-strapi-project.git
        git add .
        git commit -m "Initial commit"
        git push -u origin master


- Deploy(Deploying Strapi on AWS EC2)
    1. Launch an EC2 Instance: Use an appropriate Amazon Machine Image (AMI) and instance type.
    2. SSH into Your EC2 Instance:
            ssh -i "your-key.pem" ec2-user@<your-public-ip>
    3. Install Dependencies: Install Node.js, npm, and other necessary packages.
    4. Clone Your GitHub Repository:
            git clone https://github.com/username/my-strapi-project.git
            cd strapi-project
    5. Install Project Dependencies:
            npm install
    6. Start Strapi:
            npm run start
    7. Setting Up Firewall
        >> Go to the EC2 Management Console.
        >> Select "Security Groups" associated with your EC2 instance.
        >> Edit Inbound Rules:
                Type: Custom TCP Rule
                Protocol: TCP
                Port Range: 1337
                Source: 0.0.0.0/0 
    This configuration will allow access to the Strapi application from anywhere on the internet.
