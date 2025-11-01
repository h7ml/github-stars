---
project: mcp-server-chart
stars: 3072
description: 🤖 A visualization mcp contains 25+ visual charts using @antvis. Using for chart generation and data analysis.
url: https://github.com/antvis/mcp-server-chart
---

MCP Server Chart
================

A Model Context Protocol server for generating charts using AntV. We can use this mcp server for _chart generation_ and _data analysis_.

This is a TypeScript-based MCP server that provides chart generation capabilities. It allows you to create various types of charts through MCP tools. You can also use it in Dify.

📋 Table of Contents
--------------------

-   ✨ Features
-   🤖 Usage
-   🚰 Run with SSE or Streamable transport
-   🎮 CLI Options
-   ⚙️ Environment Variables
    -   VIS\_REQUEST\_SERVER
    -   SERVICE\_ID
    -   DISABLED\_TOOLS
-   📠 Private Deployment
-   🗺️ Generate Records
-   🎛️ Tool Filtering
-   🔨 Development
-   📄 License

✨ Features
----------

Now 25+ charts supported.

1.  `generate_area_chart`: Generate an `area` chart, used to display the trend of data under a continuous independent variable, allowing observation of overall data trends.
2.  `generate_bar_chart`: Generate a `bar` chart, used to compare values across different categories, suitable for horizontal comparisons.
3.  `generate_boxplot_chart`: Generate a `boxplot`, used to display the distribution of data, including the median, quartiles, and outliers.
4.  `generate_column_chart`: Generate a `column` chart, used to compare values across different categories, suitable for vertical comparisons.
5.  `generate_district_map` - Generate a `district-map`, used to show administrative divisions and data distribution.
6.  `generate_dual_axes_chart`: Generate a `dual-axes` chart, used to display the relationship between two variables with different units or ranges.
7.  `generate_fishbone_diagram`: Generate a `fishbone` diagram, also known as an Ishikawa diagram, used to identify and display the root causes of a problem.
8.  `generate_flow_diagram`: Generate a `flowchart`, used to display the steps and sequence of a process.
9.  `generate_funnel_chart`: Generate a `funnel` chart, used to display data loss at different stages.
10.  `generate_histogram_chart`: Generate a `histogram`, used to display the distribution of data by dividing it into intervals and counting the number of data points in each interval.
11.  `generate_line_chart`: Generate a `line` chart, used to display the trend of data over time or another continuous variable.
12.  `generate_liquid_chart`: Generate a `liquid` chart, used to display the proportion of data, visually representing percentages in the form of water-filled spheres.
13.  `generate_mind_map`: Generate a `mind-map`, used to display thought processes and hierarchical information.
14.  `generate_network_graph`: Generate a `network` graph, used to display relationships and connections between nodes.
15.  `generate_organization_chart`: Generate an `organizational` chart, used to display the structure of an organization and personnel relationships.
16.  `generate_path_map` - Generate a `path-map`, used to display route planning results for POIs.
17.  `generate_pie_chart`: Generate a `pie` chart, used to display the proportion of data, dividing it into parts represented by sectors showing the percentage of each part.
18.  `generate_pin_map` - Generate a `pin-map`, used to show the distribution of POIs.
19.  `generate_radar_chart`: Generate a `radar` chart, used to display multi-dimensional data comprehensively, showing multiple dimensions in a radar-like format.
20.  `generate_sankey_chart`: Generate a `sankey` chart, used to display data flow and volume, representing the movement of data between different nodes in a Sankey-style format.
21.  `generate_scatter_chart`: Generate a `scatter` plot, used to display the relationship between two variables, showing data points as scattered dots on a coordinate system.
22.  `generate_treemap_chart`: Generate a `treemap`, used to display hierarchical data, showing data in rectangular forms where the size of rectangles represents the value of the data.
23.  `generate_venn_chart`: Generate a `venn` diagram, used to display relationships between sets, including intersections, unions, and differences.
24.  `generate_violin_chart`: Generate a `violin` plot, used to display the distribution of data, combining features of boxplots and density plots to provide a more detailed view of the data distribution.
25.  `generate_word_cloud_chart`: Generate a `word-cloud`, used to display the frequency of words in textual data, with font sizes indicating the frequency of each word.

Note

The above geographic visualization chart generation tool uses AMap service and currently only supports map generation within China.

🤖 Usage
--------

To use with `Desktop APP`, such as Claude, VSCode, Cline, Cherry Studio, Cursor, and so on, add the MCP server config below. On Mac system:

{
  "mcpServers": {
    "mcp-server-chart": {
      "command": "npx",
      "args": \["\-y", "@antv/mcp-server-chart"\]
    }
  }
}

On Window system:

{
  "mcpServers": {
    "mcp-server-chart": {
      "command": "cmd",
      "args": \["/c", "npx", "\-y", "@antv/mcp-server-chart"\]
    }
  }
}

Also, you can use it on aliyun, modelscope, glama.ai, smithery.ai or others with HTTP, SSE Protocol.

🚰 Run with SSE or Streamable transport
---------------------------------------

### Run directly

Install the package globally.

npm install -g @antv/mcp-server-chart

Run the server with your preferred transport option:

# For SSE transport (default endpoint: /sse)
mcp-server-chart --transport sse

# For Streamable transport with custom endpoint
mcp-server-chart --transport streamable

Then you can access the server at:

-   SSE transport: `http://localhost:1122/sse`
-   Streamable transport: `http://localhost:1122/mcp`

### Docker deploy

Enter the docker directory.

cd docker

Deploy using docker-compose.

docker compose up -d

Then you can access the server at:

-   SSE transport: `http://localhost:1123/sse`
-   Streamable transport: `http://localhost:1122/mcp`

🎮 CLI Options
--------------

You can also use the following CLI options when running the MCP server. Command options by run cli with `-H`.

```
MCP Server Chart CLI

Options:
  --transport, -t  Specify the transport protocol: "stdio", "sse", or "streamable" (default: "stdio")
  --host, -h       Specify the host for SSE or streamable transport (default: localhost)
  --port, -p       Specify the port for SSE or streamable transport (default: 1122)
  --endpoint, -e   Specify the endpoint for the transport:
                   - For SSE: default is "/sse"
                   - For streamable: default is "/mcp"
  --help, -H       Show this help message
```

⚙️ Environment Variables
------------------------

Variable

Description

Default

Example

`VIS_REQUEST_SERVER`

Custom chart generation service URL for private deployment

`https://antv-studio.alipay.com/api/gpt-vis`

`https://your-server.com/api/chart`

`SERVICE_ID`

Service identifier for chart generation records

\-

`your-service-id-123`

`DISABLED_TOOLS`

Comma-separated list of tool names to disable

\-

`generate_fishbone_diagram,generate_mind_map`

### 📠 Private Deployment

`MCP Server Chart` provides a free chart generation service by default. For users with a need for private deployment, they can try using `VIS_REQUEST_SERVER` to customize their own chart generation service.

{
  "mcpServers": {
    "mcp-server-chart": {
      "command": "npx",
      "args": \["\-y", "@antv/mcp-server-chart"\],
      "env": {
        "VIS\_REQUEST\_SERVER": "<YOUR\_VIS\_REQUEST\_SERVER>"
      }
    }
  }
}

You can use AntV's project GPT-Vis-SSR to deploy an HTTP service in a private environment, and then pass the URL address through env `VIS_REQUEST_SERVER`.

-   **Method**: `POST`
-   **Parameter**: Which will be passed to `GPT-Vis-SSR` for rendering. Such as, `{ "type": "line", "data": [{ "time": "2025-05", "value": 512 }, { "time": "2025-06", "value": 1024 }] }`.
-   **Return**: The return object of HTTP service.
    -   **success**: `boolean` Whether generate chart image successfully.
    -   **resultObj**: `string` The chart image url.
    -   **errorMessage**: `string` When `success = false`, return the error message.

Note

The private deployment solution currently does not support geographic visualization chart generation include 3 tools: `geographic-district-map`, `geographic-path-map`, `geographic-pin-map`.

### 🗺️ Generate Records

By default, users are required to save the results themselves, but we also provide a service for viewing the chart generation records, which requires users to generate a service identifier for themselves and configure it.

Use Alipay to scan and open the mini program to generate a personal service identifier (click the "My" menu below, enter the "My Services" page, click the "Generate" button, and click the "Copy" button after success):

Next, you need to add the `SERVICE_ID` environment variable to the MCP server configuration. For example, the configuration for Mac is as follows (for Windows systems, just add the `env` variable):

{
  "mcpServers": {
    "AntV Map": {
      "command": "npx",
      "args": \["\-y", "@antv/mcp-server-chart"\],
      "env": {
        "SERVICE\_ID": "\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*"
      }
    }
  }
}

After updating the MCP Server configuration, you need to restart your AI client application and check again whether you have started and connected to the MCP Server successfully. Then you can try to generate the map again. After the generation is successful, you can go to the "My Map" page of the mini program to view your map generation records.

### 🎛️ Tool Filtering

You can disable specific chart generation tools using the `DISABLED_TOOLS` environment variable. This is useful when certain tools have compatibility issues with your MCP client or when you want to limit the available functionality.

{
  "mcpServers": {
    "mcp-server-chart": {
      "command": "npx",
      "args": \["\-y", "@antv/mcp-server-chart"\],
      "env": {
        "DISABLED\_TOOLS": "generate\_fishbone\_diagram,generate\_mind\_map"
      }
    }
  }
}

**Available tool names for filtering** See the ✨ Features.

🔨 Development
--------------

Install dependencies:

npm install

Build the server:

npm run build

Start the MCP server:

npm run start

Start the MCP server with SSE transport:

node build/index.js -t sse

Start the MCP server with Streamable transport:

node build/index.js -t streamable

📄 License
----------

MIT@AntV.
