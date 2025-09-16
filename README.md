# MCP Shield - Project Documentation

## High-Level Overview

### Project Name
**MCP Shield**

### Purpose / Description
The MCP Shield project adds an **authorization layer** to the existing MCP (Model Context Protocol) servers.  

In the current MCP implementation (as of 02/08/2025):  
- MCP servers provide **tools, prompts, resources, and templates**.  
- Every authenticated client can access all of these features without restriction.  

**MCP Shield objectives:**  
- Introduce **authorization** for clients.  
- Associate **roles and permissions** with each client.  
- Ensure that clients can **only access what they are allowed to see**, improving security and control over MCP server resources.  
- Support **server-level filters** configured by admins before the server starts, blocking certain items for all clients.

### Architecture Diagram

```mermaid
flowchart TD
    Admin[Admin] -->|Set server filters| MCPServer[MCP Server]
    Client[Client] -->|Request access token| AuthService[Authorization Service]
    AuthService -->|Generate token with roles & permissions| Client
    Client -->|Request item with token| MCPServer
    MCPServer -->|Check token roles & permissions against item requirements| AccessControl[Access Control]
    
    AccessControl -->|Access granted| Tools[Tools]
    AccessControl -->|Access granted| Prompts[Prompts]
    AccessControl -->|Access granted| Resources[Resources]
    AccessControl -->|Access granted| Templates[Templates]
    
    AccessControl -->|Access denied| Denied[Access Denied Message]
