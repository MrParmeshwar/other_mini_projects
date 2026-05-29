# Windsurf + Burp Suite MCP Integration

## Project Information

**Category:** AI + Application Security  
**Difficulty:** Beginner  
**Time Required:** ~15 Minutes  
**Tools Used:** Windsurf, Burp Suite, MCP Server, Java JDK  

## Overview

This project demonstrates how to connect Windsurf AI with Burp Suite Professional using the Burp MCP (Model Context Protocol) Server.

The integration allows Windsurf to directly interact with Burp Suite and access available MCP tools for analyzing HTTP traffic, reviewing requests and responses, and assisting with web application security testing workflows.

## Environment

* Operating System: Windows
* Burp Suite Professional/Community 
* Windsurf
* Java JDK
* Burp MCP Server Extension

## Objective

Connect Windsurf to Burp Suite through MCP and verify that Windsurf can access Burp tools and analyze captured HTTP traffic.

## Installation

### 1. Install Java JDK

Verify Java is installed:

```powershell
java -version
```

### 2. Install Windsurf

Install and launch Windsurf.

### 3. Install Burp Suite Professional

Launch Burp Suite and create a project.

### 4. Install the Burp MCP Server Extension

Navigate to:

```text
Extensions → BApp Store → MCP Server
```

Install the extension.

After installation, a new **MCP** tab becomes available in Burp Suite.

### 5. Verify MCP Server Configuration

Open:

```text
Burp → MCP
```

Default configuration:

```text
Host: 127.0.0.1
Port: 9876
```

The MCP server listens locally and exposes Burp functionality to MCP-compatible AI clients.

### 6. Configure Windsurf

Open:

```text
Profile Icon → Windsurf Settings
```

Search for:

```text
MCP
```

Select:

```text
Open MCP Registry
```

Click:

```text
Add Custom MCP
```

Create the following configuration:

```json
{
  "mcpServers": {
    "burp": {
      "url": "http://127.0.0.1:9876"
    }
  }
}
```

Save the file.

### 7. Verify Connection

After saving the configuration, Windsurf automatically connects to the Burp MCP Server.

A new MCP server named:

```text
burp
```

appears in Windsurf.

In my setup, the connection exposed 24 Burp-related tools through MCP.

## Testing

To verify functionality, I prompted Windsurf to analyze Burp Suite HTTP history.

Example prompt:

```text
Analyze the HTTP history from Burp Suite.
```

Result:

* Windsurf successfully accessed Burp data through MCP.
* HTTP requests and responses were available for analysis.
* The integration worked without requiring additional configuration.

## Use Cases

* Reviewing captured HTTP traffic
* Understanding application behavior
* Request and response analysis
* Generating testing ideas
* Assisting during bug bounty reconnaissance
* Learning web application security concepts

## Outcome

Successfully connected Windsurf AI to Burp Suite Professional using the Burp MCP Server and verified that Windsurf could access Burp tools and analyze HTTP history through MCP.

## Notes

This setup was tested on Windows using Burp Suite Professional and Windsurf with a locally running MCP server on port 9876.
