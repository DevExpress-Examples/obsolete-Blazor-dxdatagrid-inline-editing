<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/351812089/20.2.5%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T985618)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->

# DataGrid for Blazor - How to implement the inline edit mode with the DisplayTemplate

![Data Grid - Inline edit form](images/dxdatsgrid-inline-editing.gif)

<!-- run online -->
**[[Run Online]](https://codecentral.devexpress.com/351812089/)**
<!-- run online end -->

This example illustrates a possible implementation of the case when users can edit values in the inline edit row. 
The main idea of the solution is to create the [DisplayTemplate](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxDataGridColumn.DisplayTemplate) for each column and display the corresponding value or an editor based on the state of the current row. 

The **IsInEditMode** custom property defines the state of the current row. You can find the implementation of this custom property in the [WeatherForecastForEdit](./CS/BlazorGridInlineEditing/Data/WeatherForecastForEdit.cs) class. This class inherits the original [WeatherForecast](./CS/BlazorGridInlineEditing/Data/WeatherForecast.cs) model class and extends it with the **IsInEditMode** property. 

Also the **WeatherForecastForEdit** class implements the [INotifyPropertyChanged](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanged?view=net-5.0) interface. The Data Grid automatically detects such interfaces and handles the **PropertyChanged** event, so that if the corresponding property value changes, the DxDataGrid component re-renders the corresponding row. 

<!-- default file list -->
## Files to look at

* [Index.razor](./CS/BlazorGridInlineEditing/Pages/Index.razor)
* [WeatherForecast.cs](./CS/BlazorGridInlineEditing/Data/WeatherForecast.cs)
* [WeatherForecastForEdit.cs](./CS/BlazorGridInlineEditing/Data/WeatherForecastForEdit.cs)
<!-- default file list end -->

## Documentation

* [DisplayTemplate](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxDataGridColumn.DisplayTemplate)
* [EditTemplate](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxDataGridColumn.EditTemplate)

## More Examples

* [Data Grid - Update records programmatically](https://github.com/DevExpress-Examples/blazor-DxDataGrid-edit-selected-row-by-clicking-on-external-button)
* [Data Grid - Separate Edit Form](https://github.com/DevExpress-Examples/blazor-DxDataGrid-Separate-Edit-Form)