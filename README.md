
# Transport Data Ingestion Pipeline

## Table of Contents
1. [Introduction](#introduction)
2. [Tools Used](#tools-used)
3. [Data Set](#data-set)
4. [Setting Up Azure Event Hub](#setting-up-azure-event-hub)
5. [Setting Up Azure Stream Analytics](#setting-up-azure-stream-analytics)
   - [Setting Up Input as Azure Event Hub](#setting-up-input-as-azure-event-hub)
   - [Setting Up Output as SQL Database](#setting-up-output-as-sql-database)
6. [Create an SQL Database](#create-an-sql-database)
7. [Create a Table in the Database](#create-a-table-in-the-database)
8. [Run the Python Script on the Local Machine](#run-the-python-script-on-the-local-machine)
9. [Perform Your Visualization with Power BI](#perform-your-visualization-with-power-bi)
   - [Connecting to Azure SQL Database](#connecting-to-azure-sql-database)
   - [Building Visualizations](#building-visualizations)
   - [Publishing and Sharing](#publishing-and-sharing)

## Introduction <a name="introduction"></a>

This project is aimed at building a data ingestion pipeline for a transport dataset. The pipeline streams data from a local machine into Azure Event Hubs, uses Azure Stream Analytics to process this data in real-time, and stores it in an Azure SQL Database for further visualization using Power BI.

## Tools Used <a name="tools-used"></a>

- **Azure Event Hubs**: For ingesting real-time streaming data.
- **Azure Stream Analytics**: For processing the streaming data in real-time.
- **Azure SQL Database**: For storing the processed data.
- **Python**: For scripting the data ingestion from the local machine.
- **Power BI**: For visualizing the stored data and uncovering insights.
- **SQL Server Management Studio (Optional)**: For managing the SQL Database and executing SQL scripts.

## Data Set <a name="data-set"></a>

The transport dataset contains various attributes related to transportation, such as vehicle type, route, timestamp, etc. You can find the file in the data folder above

## Setting Up Azure Event Hub <a name="setting-up-azure-event-hub"></a>

1. **Create a Namespace**: Navigate to the Azure Portal, and create a new Event Hubs Namespace.
2. **Create an Event Hub**: Inside the namespace, create an Event Hub.
3. **Get Connection String**: Go to Shared access policies, create a new policy, and copy the connection string, save it somewhere for later as your Python script would need it to create a connection

## Create an SQL Database <a name="create-an-sql-database"></a>

1. **Create SQL Database**: In the Azure Portal, create a new SQL Database.
2. **Configure Database**: Set up the server, login credentials, and firewall rules to allow connections.

## Create a Table in the Database <a name="create-a-table-in-the-database"></a>

Navigate to the SQL Database created and use the SQL query window or SQL Server Management Studio to create a table that aligns with the data schema of the incoming data.

## Setting Up Azure Stream Analytics <a name="setting-up-azure-stream-analytics"></a>

### Setting Up Input as Azure Event Hub <a name="setting-up-input-as-azure-event-hub"></a>

1. **Create a Stream Analytics Job**: Navigate to Azure Portal and create a Stream Analytics job.
2. **Add Input**: In the job topology, add an input and choose Azure Event Hub. Paste the connection string copied from the Event Hub setup.

### Setting Up Output as SQL Database <a name="setting-up-output-as-sql-database"></a>

3. **Create Output**: In the job topology, add an output and select Azure SQL Database.
4. **Configure Output**: Fill in the necessary details such as SQL Database credentials, table name, etc.

## Run the Python Script on the Local Machine <a name="run-the-python-script-on-the-local-machine"></a>

Use a Python script to read the transport dataset and send events to the Azure Event Hub.

## Perform Your Visualization with Power BI <a name="perform-your-visualization-with-power-bi"></a>

### Connecting to Azure SQL Database <a name="connecting-to-azure-sql-database"></a>

1. **Open Power BI Desktop**: If you don’t have Power BI Desktop, you can [download it here](https://powerbi.microsoft.com/desktop/).
2. **Get Data**: On the Home tab, click on "Get Data".
3. **SQL Server Database**: In the Get Data window, select "SQL Server" and click on "Connect".
4. **Database Connection**: Enter the server address and database details. Use the credentials set up earlier for the Azure SQL Database.
5. **Load Data**: Select the table you have created and click on "Load".

### Building Visualizations <a name="building-visualizations"></a>

1. **Drag and Drop Fields**: Use the Fields pane to select the columns you want to visualize. Drag and drop them into the Values and Axis areas.
2. **Choose Visualization Type**: Select the type of visualization you want (e.g., bar chart, line chart, map) from the Visualizations pane.
3. **Filter and Customize**: Use filters to refine your visualization and the Format pane to customize the appearance.
4. **Create Reports and Dashboards**: Combine multiple visualizations into a report. You can also pin visualizations to a dashboard for sharing and quick access.

### Publishing and Sharing <a name="publishing-and-sharing"></a>

1. **Save Your Report**: Before publishing, save your Power BI Desktop report file (`.pbix`).
2. **Publish**: Click on the "Publish" button on the Home tab. You'll need a Power BI Pro or Power BI Premium license to share your report with others.
3. **Share**: Once published, go to the Power BI service, find your report, and use the "Share" button to share it with others.

By following these steps and using the mentioned tools, you will be able to ingest, process, store, and visualize transport data, thereby gaining valuable insights.
