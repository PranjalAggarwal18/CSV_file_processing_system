
# 🌟 CSV File Processing System 🚀

Welcome to the **CSV File Processing System**! If you're ready to dive into the world of cloud computing, metadata extraction, and AWS-like local environments, you're in the right place. Let's explore how this project makes file handling easy and efficient in a cloud-like local environment using **LocalStack**.

## ✨ What is this Project? 🤔

This project is a **cloud-based file processing system** designed to handle **CSV files** with ease. It automatically:

1. **Uploads CSV files** to an S3 bucket.
2. **Extracts metadata** like:
   - Row count 📊
   - Column count 📏
   - Column names 📝
3. **Stores this metadata** in a **database** (DynamoDB or RDS).
4. (Optional) Sends a **notification** upon completion. 🛎️

What’s awesome? This entire setup is running locally using **LocalStack** – an open-source tool that simulates AWS services on your machine. No AWS account? No problem. 🙌

---

## 🔧 Technologies Used

Here’s what powers this project:

- **S3**: Cloud storage for CSV files.
- **Lambda**: Serverless function to process CSV files and extract metadata.
- **DynamoDB or RDS**: Choose a database to store metadata (you can use whichever suits your project best).
- **LocalStack**: Local AWS cloud stack emulator to develop and test without AWS costs.
- **Python**: The programming language that ties everything together! 🐍

---

## 🚀 Getting Started

Let’s get this system up and running in your local environment. Follow these steps to get started:

### 🛠️ Prerequisites
Before you begin, make sure you have the following installed on your machine:

- **Python 3.x**
- **LocalStack** (this simulates the AWS cloud locally)
- **Docker** (required by LocalStack)
- **AWS CLI** (Optional, for interacting with LocalStack services)

### 1️⃣ Install LocalStack

LocalStack is the backbone of this project. It allows you to simulate AWS services locally without the need for real AWS credentials.

- **Installation via Docker**:  
  If you don’t have Docker installed, get it [here](https://www.docker.com/get-started).

  Then, run LocalStack with the following command:
  ```bash
  docker-compose up
  ```

- Alternatively, you can install LocalStack with pip:
  ```bash
  pip install localstack
  ```

### 2️⃣ Set Up the Project

Clone this repository to your local machine:
```bash
git clone https://github.com/KritikaK21/FileProcessingSystem.git
cd FileProcessingSystem
```

Now, you’re ready to go!

---

## ⚡ How It Works

The magic happens with just a few simple steps! Here’s the entire flow:

### 🗂️ Step 1: Upload a CSV to S3

Once you run the system, it automatically uploads the **CSV** to an **S3 bucket**.

- Simply place your CSV file in the designated folder or use the provided UI (if available).
- The Lambda function will be triggered once the file is uploaded to the bucket.

### 📊 Step 2: Metadata Extraction

Here’s where things get interesting. Our Lambda function will automatically:

- Count the **rows** and **columns** in the CSV file.
- Get the **column names**.
  
Example metadata:
```json
{
  "filename": "example.csv",
  "upload_timestamp": "2024-12-14 10:00:00",
  "file_size_bytes": 1048576,
  "row_count": 1000,
  "column_count": 5,
  "column_names": ["id", "name", "age", "city", "date"]
}
```

### 🗄️ Step 3: Store Metadata in Database

Next, the extracted metadata is stored in your chosen database. You can either go with:

- **DynamoDB**: A NoSQL option for easy and fast metadata storage.
- **RDS (PostgreSQL or MySQL)**: A relational database for more complex needs.

### 🔔 Step 4: Get a Notification (Optional)

If you want, the system will send a notification once the process is complete. This could be done using AWS SNS (Simple Notification Service) for real-time updates.

---

## 🔍 Explore the Code

The heart of this system is in the code files:

- **localstack_s3.py**: Responsible for interacting with S3.
- **s3_client.py**: The script that interacts with the LocalStack S3 service to upload and retrieve files.
- **metadata_extractor.py**: The magic that extracts metadata from your CSV files.
- **lambda_function.py**: Handles the Lambda function that triggers upon file upload.
- **db_connector.py**: Connects to the database and stores metadata.

---

## 📝 Example Workflow

Let’s break down the workflow using an example:

1. **Upload** your CSV file, e.g., `data.csv`, to the LocalStack S3 bucket.
2. The **Lambda function** is triggered automatically. It processes the file and extracts metadata.
3. The extracted metadata (like row count, column names) is stored in **DynamoDB** (or RDS).
4. You get a notification (optional) about the successful upload and processing.

---

## 💡 Why Use LocalStack?

### 🎯 **Test AWS Services Locally**:
LocalStack emulates many AWS services locally, allowing you to develop and test your cloud-based applications without incurring any costs.

### ⏱️ **Speed Up Development**:
Instead of waiting for cloud resources to spin up on AWS, LocalStack provides an instant local environment for faster development and testing.

### 💸 **No AWS Costs**:
When developing and testing locally with LocalStack, you won’t be charged for any AWS resources.

---

## 📈 Future Enhancements

- **UI Dashboard**: A simple web UI to upload CSV files, view metadata, and check the status of your files.
- **More File Formats**: Support for JSON, XML, and other file types.
- **Cloud Deployment**: After local testing, deploy the system to real AWS services!

---

## 🏆 Conclusion

This project combines the best of **cloud computing** and **local testing** to make file processing easier and more efficient. Whether you're learning cloud technologies or building a robust system, this project gives you a strong foundation.

---



---

**Ready to dive in?** 🎉

- Clone the repo, set up LocalStack, and get started with cloud-based CSV processing today! 🚀# CSV_file_processing_system
csv file processing system
