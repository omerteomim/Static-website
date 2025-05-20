# Static Website with CloudFront and S3

A simple static website hosted on AWS S3 and delivered globally through CloudFront CDN.

## About This Project

This repository contains a static website with HTML and CSS, configured with a CI/CD pipeline for automatic deployment to AWS. The website is securely served via HTTPS using AWS services.

## Infrastructure

This website uses the following AWS services:
- **S3**: For storing the static files (HTML, CSS)
- **CloudFront**: Content delivery network for global distribution
- **Route 53**: DNS management
- **ACM**: SSL/TLS certificate for HTTPS

## Deployment

The website is automatically deployed whenever changes are pushed to the main branch. The deployment workflow:

1. Uploads the files to the S3 bucket
2. Invalidates the CloudFront cache to make changes immediately visible

## Local Development

To work on this website locally:

1. Clone this repository
2. Make changes to the HTML and CSS files
3. Test by opening the HTML file in your browser
4. Commit and push your changes to deploy them

## Repository Structure

```
.
├── index.html              # Main HTML file
├── index.css               # CSS styling
├── .github/
│   └── workflows/
│       └── deploy.yml      # GitHub Actions workflow file
└── README.md               # This documentation file
```

## Setup Instructions

To set up a similar project:

1. Create an S3 bucket for static website hosting
2. Set up CloudFront distribution pointing to the S3 bucket
3. Configure Route 53 with your domain
4. Request an SSL certificate through ACM
5. Set up GitHub Actions with the necessary secrets:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
   - `AWS_S3_BUCKET`
   - `CLOUDFRONT_DISTRIBUTION_ID`
