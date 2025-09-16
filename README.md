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

### Architecture Diagram

```mermaid
flowchart LR
    Client[Client]
    AuthService[Authorization Service]
    MCPServer[MCP Server]
    Tools[Tools]
    Prompts[Prompts]
    Resources[Resources]
    Templates[Templates]

    Client -->|Authentication & Requests| AuthService
    AuthService -->|Access Control Checks| MCPServer
    MCPServer --> Tools
    MCPServer --> Prompts
    MCPServer --> Resources
    MCPServer --> Templates
