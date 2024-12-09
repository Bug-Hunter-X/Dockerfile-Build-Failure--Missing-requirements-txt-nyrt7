# Dockerfile Bug: Missing requirements.txt

This repository demonstrates a common error in Dockerfiles: the failure to include a required file (`requirements.txt` in this case) in the build context.  The Dockerfile attempts to install Python packages using `pip3 install -r requirements.txt`, but the file is missing, leading to a build failure.

The solution demonstrates how to properly include the requirements file in the context and build the Docker image successfully.

## Bug
The initial `Dockerfile` attempts to install packages using a non-existent `requirements.txt`.

## Solution
The solution `Dockerfile_solution` demonstrates the correct approach, ensuring the `requirements.txt` file is included in the build context.

## How to reproduce
1. Clone this repository.
2. Attempt to build the original `Dockerfile` using `docker build -t my-app .` (This will fail)
3. Build the `Dockerfile_solution` using `docker build -t my-app-solution .` (This will succeed)