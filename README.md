# docker-lamp-php-legacy (PHP 7.4 / MySQL 5.7)

## Description

This is for my own use. Feel free to fork and update for your needs!!!

## Prerequisites

Before you begin, ensure you have met the following requirements:
- You have installed Docker.
- You have installed Git.

## 1 Cloning the Repository

Follow these simple steps:

 - Clone the repository:
    ```bash
    git clone git@github.com:leandro-serfe/docker-lamp-php-legacy.git
    ```
   
 - Navigate into the cloned repository:
    ```bash
    cd docker-lamp-php-legacy
    ```

## 2 Overriding the .env File

To set up the environment variables, you need to create or override the `.env` file in the `docker-lamp-php-legacy` folder with your specific configurations. Here’s how you can do it:

 - Create or copy the `.env` file in the `docker-lamp-php-legacy` folder:
    ```bash    
    cp .env.copy .env
    ```
   
 - Open the `.env` file and add your desired environment variables values. An example `.env` file might look like this:
    ```env    
    MYSQL_ROOT_PASSWORD=yoursecurepass
    MYSQL_DATABASE=db
    MYSQL_USER=legacy
    MYSQL_PASSWORD=yoursecurepass
    ```

## Customizing the Dockerfile

If you need to customize the Docker configuration, you can override the existing `Dockerfile` in the `server` folder. Follow these steps:

1. Navigate to the `docker` folder:

2. Edit the `docker/Dockerfile` according to your requirements.

3. Make sure you install all extensions and enable apache modules there. Read more in [Use containers for PHP development](https://docs.docker.com/language/php/develop/)


## Moving Files into the "server" Folder

Ensuring that Docker and other configurations are correctly set up, all necessary files for your PHP web server should be moved into the `server` folder. 

Ensure the directory structure is similar to the following:

```
docker-lamp-php-legacy/
├── docker/
│   ├── Dockerfile
│   └── other-docker-settings-files
├── server/
│   ├── index.php
│   └── {copy here your PHP framework}
├── logs/
├── .env
├── docker-compose.yml
├── README.md
└── other-project-files
```

## Running the Application

To run the application using Docker, execute the following commands:

1. Build the Docker image:
    ```bash
    docker-compose build .
    ```

2. Run the Docker container:
    ```bash
    docker-compose up -d
    ```

The application should now be running on http://localhost:8000

You can access PMA at http://localhost:8080

## Contributing

If you have any suggestions or want to contribute to the project, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
