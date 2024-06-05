# eInvoice Java Console Application

This Java console application retrieves invoice information from a database using JDBC and DAOs, constructs an example JSON using Jackson, and interacts with an eInvoice web service.

## Project Structure
- **dao**: Contains Data Access Object (DAO) classes responsible for interacting with database views.
- **model**: Contains corresponding model classes representing data objects.
- **connection**: Includes a singleton class (`GetConnection`) for managing database connections.
- **util**: Houses utility classes for date formatting (`DateUtils`) and JSON manipulation (`JsonUtils`).
- **service**: Main class (`Main`) for creating documents and starting the application.


## Installation

### Before proceeding :
* Make sure you have Docker installed on your system.
* In order to access the network and connect to the database via JDBC from inside the container, you need to add the following settings to your  Docker Daemon configuration.

```json
{
  "builder": {
    "gc": {
      "defaultKeepStorage": "20GB",
      "enabled": true
    }
  },
  "default-address-pools": [
    {
      "base": "10.222.0.0/16",
      "size": 24
    }
  ],
  "experimental": false
}
```

### Step 1: Clone the Repository

Clone the project repository to your local machine using the following command:

```bash
git clone https://git.neuropublic.gr/g_markozanis/einvoice.git
```
### Step 2: Navigate to the Project Directory

Navigate to the directory where the project is cloned:
```bash
cd eInvoice
```

### Step 3: Build and Run with Docker

Execute the following Docker commands to build and run the application:

```bash
# Build the Docker image for the eInvoice application
docker build -t einvoice-app .

# Run the Docker container interactively and remove it after exiting
docker run -it --rm einvoice-app
```

## How to Use

To use the application, follow these steps:

1. Once you complete the installation (see [Installation](#installation)), the application automatically runs inside a container and prompts you to enter a trhe_id.
2. Enter a valid trhe_id, in order to get the appropriate JSON document for the EINVOICING's POST.
3. To exit, simply enter "stop" when prompted.


