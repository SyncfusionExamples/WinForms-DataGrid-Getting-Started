# WinForms SfDataGrid Getting Started

## Overview

This demo shows how to create a simple sample in [WinForms SfDataGrid](https://www.syncfusion.com/winforms-ui-controls/datagrid?utm_source=github&utm_medium=listing&utm_campaign=winforms-datagrid-github-samples). The sample demonstrates the basic setup and usage of the Syncfusion WinForms DataGrid control to display order data in a tabular format.

## Key Features

- Display data in a DataGrid control
- Automatic column generation from data source
- Simple [data binding](https://help.syncfusion.com/windowsforms/datagrid/databinding?utm_source=github&utm_medium=listing&utm_campaign=winforms-datagrid-github-samples) to the DataGrid

## Getting Started

1. **Create a Windows Forms Application**: Start with a new Windows Forms project
2. **Add SfDataGrid Control**: Add the Syncfusion DataGrid control to your form
3. **Bind Data to DataGrid**: Assign your data collection to the DataGrid's `DataSource` property
4. **Run the Application**: The DataGrid displays the data in columns and rows

## Code Example

### Binding Data to SfDataGrid

The following code demonstrates how to bind a data collection to the SfDataGrid control:

```csharp
using Syncfusion.WinForms.DataGrid;

public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        // Bind the data collection to the DataGrid
        sfDataGrid1.DataSource = new OrderInfoCollection().OrdersListDetails;
    }
}
```

### Creating a Data Collection

Create a collection class that provides data to the DataGrid:

```csharp
public class OrderInfoCollection : IDisposable
{
    public OrderInfoCollection()
    {
        OrdersListDetails = new OrderInfoRepository().GetListOrdersDetails(100);
    }

    public List<OrderInfo> OrdersListDetails { get; set; }

    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    protected virtual void Dispose(bool isdisposable)
    {
        if (this.OrdersListDetails != null)
        {
            this.OrdersListDetails.Clear();
        }
    }
}
```

## Requirements

- Windows Forms Application (.NET Framework or .NET)
- Syncfusion WinForms DataGrid control library

## Documentation

For more information about the SfDataGrid control and its features, refer to the official documentation:
[WinForms DataGrid Getting Started](https://help.syncfusion.com/windowsforms/datagrid/gettingstarted?utm_source=github&utm_medium=listing&utm_campaign=winforms-datagrid-github-samples)
