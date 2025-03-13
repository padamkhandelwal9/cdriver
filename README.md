# Multithreaded Proxy Server with Caching

## Overview

This project implements a multithreaded HTTP proxy server with caching capabilities. The proxy server handles multiple client requests concurrently, forwards them to the appropriate remote servers, and caches the responses to improve performance for subsequent requests.

## Features

- **Multithreading**: Handles multiple client requests simultaneously using POSIX threads.
- **Caching**: Caches responses from remote servers to serve repeated requests quickly.
- **LRU Cache Eviction**: Implements Least Recently Used (LRU) cache eviction policy to manage cache size.
- **Error Handling**: Sends appropriate HTTP error responses for various error conditions.

## Project Structure
── .gitignore ├── Makefile ├── prac ├── proxy_parse.c ├── proxy_parse.h ├── proxy_server_with_cache.c └── .vscode/ ├── launch.json ├── settings.json └── tasks.json


- **proxy_parse.c**: Contains functions for parsing HTTP requests.
- **proxy_parse.h**: Header file for `proxy_parse.c`.
- **proxy_server_with_cache.c**: Main implementation of the proxy server with caching.
- **Makefile**: Build instructions for the project.
- **.gitignore**: Specifies files and directories to be ignored by Git.
- **.vscode/**: Contains Visual Studio Code configuration files.

## Getting Started

### Prerequisites

- GCC compiler
- POSIX-compliant operating system (e.g., Linux)

### Building the Project

To build the project, run the following command:
make

Running the Proxy Server
To start the proxy server, run the following command:
./proxy <port_number>




![Image](https://github.com/user-attachments/assets/75101cac-5043-48ee-8815-dfb1553e7f46)


![image](https://github.com/user-attachments/assets/d5776cf5-2a62-49a6-a4f1-3fcd5241bbcd)


Code Explanation
proxy_server_with_cache.c
This file contains the main implementation of the proxy server. Key functions include:

main: Initializes the server, creates threads for handling client requests, and manages the server lifecycle.
thread_fn: Handles incoming client requests in separate threads.
handle_request: Forwards client requests to remote servers and caches the responses.
sendErrorMessage: Sends appropriate HTTP error responses to clients.
connectRemoteServer: Establishes a connection to the remote server.
find: Searches for a URL in the cache.
add_cache_element: Adds a new element to the cache.
remove_cache_element: Removes the least recently used element from the cache.
proxy_parse.c and proxy_parse.h
These files contain functions for parsing HTTP requests. 

Key functions include:

ParsedRequest_create: Creates a new ParsedRequest object.
ParsedRequest_parse: Parses an HTTP request buffer into a ParsedRequest object.
ParsedRequest_unparse: Converts a ParsedRequest object back into an HTTP request buffer.
ParsedHeader_set: Sets a header key-value pair in a ParsedRequest object.
ParsedHeader_get: Retrieves a header value by key from a ParsedRequest object.
ParsedHeader_remove: Removes a header key-value pair from a ParsedRequest object.





