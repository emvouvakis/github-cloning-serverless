# GitHub Cloning Lambda 🚀

This project contains a Serverless application that periodically checks the clone counts of specified GitHub repositories and updates a DynamoDB table with the latest counts. It also sends an email with the clone statistics. 📊📧

## Features ✨

- **Scheduled Execution**: Runs every 14 days to fetch the latest clone counts from GitHub. ⏰
- **GitHub Integration**: Uses the GitHub API to retrieve clone counts for specified repositories. 📈
- **DynamoDB Storage**: Stores historical clone counts in a DynamoDB table. 📦
- **Email Notifications**: Sends an email with the latest and total clone counts. 📬

## How It Works 🛠️

1. **Fetch Clone Counts**: The Lambda function fetches the clone counts for a list of specified repositories from the GitHub API.
2. **Update DynamoDB**: The function updates a DynamoDB table with the latest clone counts.
3. **Send Email**: An email is sent with the latest clone counts and the total counts from the DynamoDB table.

## Environment Variables 🌍

- `SNS_ARN`: The ARN of the SNS topic to send email notifications.
- `GITHUB_TOKEN`: The GitHub token used for authentication with the GitHub API.

## Configuration ⚙️

The configuration for the Serverless application is defined in `serverless.yml`. This includes the schedule for the Lambda function, the DynamoDB table configuration, and the environment variables.

## Requirements 📋

- AWS account with necessary permissions.
- GitHub token with access to the repositories you want to monitor.

## Creating a GitHub Token 🔑

1. Go to [GitHub Settings](https://github.com/settings/profile).
2. In the left sidebar, click **Developer settings**.
3. In the left sidebar, click **Personal access tokens**.
4. Click **Generate new token**.
5. Give your token a descriptive name.
6. Select the scopes or permissions you'd like to grant this token. For this project, you'll need at least the `repo` scope.
7. Click **Generate token**.
8. Copy the token to a secure location. You won't be able to see it again!

Use this token as the value for the `GITHUB_TOKEN` environment variable in your configuration.

