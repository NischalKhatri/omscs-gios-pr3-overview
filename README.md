# IPC: Inter-Process Communication

## Project Overview

This project builds upon [omscs-gios-pr1-overview](https://github.com/NischalKhatri/omscs-gios-pr1-overview), transforming the GetFile server into a multi-threaded proxy server and then extending it to include a cache server. The cache server uses shared memory and other inter-process communication (IPC) mechanisms to communicate with the proxy server, enhancing efficiency and performance.

## Technologies Used

- **Programming Languages:** C
- **Libraries and APIs:** POSIX Threads (pthreads), Sockets API, libcurl, System V/POSIX Shared Memory
- **Tools:** Docker, Gradescope, Visual Studio Code

## Project Structure

### 1. Proxy Server

Implemented a proxy server that acts as an intermediary between a client and the actual server where content is hosted. The proxy server handles HTTP requests using the cURL library to retrieve and send file content over the network.

- **webproxy.c**: Main file for the webproxy program.
- **handle_with_curl.c**: Implements the handle_with_curl function using the libcurl library.

### 2. Proxy-Cache Server

Extended the proxy server to include a cache server using shared memory for data transfer and message queues for command communication. The cache server stores and serves cached content, improving performance for frequently accessed resources.

- **simplecached.c**: Main file for the cache daemon process.
- **shm_channel.c**: Implements the protocol for IPC using shared memory and message queues.
- **handle_with_cache.c**: Implements the handle_with_cache function to communicate with the cache server.

## Key Features

### Proxy Server

- **Multi-threading**: Handles multiple client requests concurrently using pthreads.
- **HTTP Requests with cURL**: Uses the cURL library to send HTTP requests to the actual server and handle responses.

### Proxy-Cache Server

- **Shared Memory for Data Transfer**: Efficiently transfers content between the proxy and cache servers using shared memory.
- **Message Queues for Command Communication**: Uses message queues to send commands and responses between the proxy and cache servers.
- **Synchronization with Semaphores**: Ensures data integrity and coordination using semaphores.

## Usage
- **Proxy Server: Acts as an intermediary to handle client requests and forward them to the actual server.
- **Proxy-Cache Server: Enhances the proxy server by caching frequently accessed content for faster retrieval.

## Original Repository
- The original project repository is private since this project was built as part of a class, but I am happy to share it for interview purposes. You can find the original project [GIOS-PR3](https://github.com/NischalKhatri/omscs-gios-pr3). Please reach out to me via email if you would like to access the full repository.
