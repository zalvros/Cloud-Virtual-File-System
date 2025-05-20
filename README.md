# Cloud-Based Virtual File System (CBVFS)

## Overview

This project is a cloud-based virtual file system that allows users to upload, store, and manage files using AWS S3 storage. The system includes a web interface with multiple pages for navigation, file uploads, and information about the platform.

## Features

- **File Upload**: Users can upload files to AWS S3 through a simple web interface.
- **Responsive Design**: Clean and modern UI with gradient backgrounds and consistent styling.
- **Multi-page Navigation**: Includes Home, Upload, About, and Contact pages.
- **AWS S3 Integration**: Secure file storage using Amazon S3 cloud service.

## Project Structure

```
.
├── upload.php           # PHP script for handling file uploads to AWS S3
├── index.html           # Main landing page with introduction to the system
├── home.html            # Home page with feature highlights
├── upload.html          # File upload interface
├── about.html           # Information about the platform
├── contact.html         # Contact form and information
└── style.css            # CSS stylesheet for all pages
```

## Setup Instructions

### Prerequisites

- Web server with PHP support (e.g., Apache, Nginx)
- AWS account with S3 access
- Composer (for PHP dependencies)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/cloud-based-file-system.git
   ```

2. Install PHP dependencies:
   ```bash
   composer require aws/aws-sdk-php
   ```

3. Configure AWS credentials in `upload.php`:
   ```php
   $s3 = new S3Client([
       'region'  => 'us-east-1',
       'version' => 'latest',
       'credentials' => [
           'key'    => 'YOUR_AWS_ACCESS_KEY',
           'secret' => 'YOUR_AWS_SECRET_KEY',
       ]
   ]);
   ```

4. Set your S3 bucket name in `upload.php`:
   ```php
   $bucketName = 'your-bucket-name';
   ```

5. Upload all files to your web server.

## Security Note

⚠️ **Important**: The current `upload.php` contains exposed AWS credentials. Before deploying:

1. Remove or replace all AWS credentials in the code
2. Use environment variables or a secure configuration file
3. Never commit sensitive credentials to version control

## Usage

1. Access the website through your web browser
2. Navigate to the Upload page
3. Select a file and click "Upload"
4. The file will be stored in your AWS S3 bucket

## Pages

- **Home**: Introduction to the cloud-based file system
- **Upload**: Interface for uploading files to S3
- **About**: Information about the platform and its features
- **Contact**: Contact form and company information

## Technologies Used

- HTML5
- CSS3
- PHP
- AWS SDK for PHP
- Amazon S3

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

