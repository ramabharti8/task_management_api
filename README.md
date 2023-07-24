# # Task Management API using Go-Gin Framework

This repository contains a Task Management API built using the Go-Gin Framework. The API allows software development teams to track and organize their tasks efficiently. It provides endpoints to create, retrieve, update, delete, and list tasks.

## Table of Contents

- [Database Schema](#database-schema)
- [API Endpoints](#api-endpoints)
  - [Create a new task](#create-a-new-task)
  - [Retrieve a task](#retrieve-a-task)
  - [Update a task](#update-a-task)
  - [Delete a task](#delete-a-task)
  - [List all tasks](#list-all-tasks)
- [Expected Output](#expected-output)

## Database Schema

The SQLite database schema for storing tasks includes the following fields:

- ID: The unique identifier for each task.
- Title: The title or name of the task.
- Description: A brief description of the task.
- Due Date: The deadline or due date for the task.
- Status: The status of the task (e.g., "pending," "completed," "in progress," etc.).

## API Endpoints

### Create a new task

- Endpoint: `POST /tasks`
- Description: Accepts a JSON payload containing the task details (title, description, due date). Generates a unique ID for the task and stores it in the database. Returns the created task with the assigned ID.

### Retrieve a task

- Endpoint: `GET /tasks/{id}`
- Description: Accepts a task ID as a parameter. Retrieves the corresponding task from the database. Returns the task details if found, or an appropriate error message if not found.

### Update a task

- Endpoint: `PUT /tasks/{id}`
- Description: Accepts a task ID as a parameter. Accepts a JSON payload containing the updated task details (title, description, due date). Updates the corresponding task in the database. Returns the updated task if successful, or an appropriate error message if not found.

### Delete a task

- Endpoint: `DELETE /tasks/{id}`
- Description: Accepts a task ID as a parameter. Deletes the corresponding task from the database. Returns a success message if the deletion is successful, or an appropriate error message if not found.

### List all tasks

- Endpoint: `GET /tasks`
- Description: Retrieves all tasks from the database. Returns a list of tasks, including their details (title, description, due date).

## Expected Output

For each API endpoint, the expected output will be as follows:

#### Create a new task

- If the request is valid and successful, the API will respond with the created task object including the assigned ID.
- If the request is invalid (e.g., missing required fields) or encounters a database error, the API will respond with an appropriate error message.

#### Retrieve a task

- If the task with the given ID exists in the database, the API will respond with the task details.
- If the task with the given ID does not exist, the API will respond with an appropriate error message.

#### Update a task

- If the task with the given ID exists in the database and the update is successful, the API will respond with the updated task details.
- If the task with the given ID does not exist or the update encounters a database error, the API will respond with an appropriate error message.

#### Delete a task

- If the task with the given ID exists in the database and the deletion is successful, the API will respond with a success message.
- If the task with the given ID does not exist, the API will respond with an appropriate error message.

#### List all tasks

- If there are tasks stored in the database, the API will respond with a list of tasks, including their details.
- If there are no tasks in the database, the API will respond with an empty list.

## Getting Started

To set up and run the Task Management API on your local machine, follow the instructions in the [Installation](#installation) section of this README.

## Installation

1. Clone this repository to your local machine.
2. Install Go and make sure Go is properly configured.
3. Install SQLite if you don't have it installed already.
4. Navigate to the project directory and install the necessary dependencies by running the following command:

```bash
go mod download
```

5. Run the API server using the following command:

```bash
go run main.go
```

The API will be accessible at `http://localhost:8080/`.
