---
layout: post
title: Data Validation in WPF DataGrid control | Syncfusion
description: Learn here all about Data Validation support in Syncfusion WPF DataGrid (SfDataGrid) control and more.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Data Validation in WPF DataGrid (SfDataGrid)

SfDataGrid allows you to validate the data and display hints in case of validation is not passed. In case of invalid data, error icon is displayed at the top right corner of [GridCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCell.html). When mouse over the error icon, error information will be displayed in tooltip.
 
## Built-in validations

Built-in validations through `IDataErrorInfo`, `INotifyDataErrorInfo` and Data annotation attributes, can be enabled by setting [SfDataGrid.GridValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridValidationMode) or [GridColumn.GridValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_GridValidationMode) properties.

 `GridColumn.GridValidationMode` takes priority than `SfDataGrid.GridValidationMode`.
 
* `GridValidation.InEdit` - display error icon & tips and also doesn’t allows the users to commit the invalid data without allowing users to edit other cells.
* `GridValidation.InView` - displays error icons and tips alone.
* `GridValidation.None` - disables built-in validation support.

## Built-in validation using IDataErrorInfo / INotifyDataErrorInfo

SfDataGrid provides support to validate the data based on [IDataErrorInfo](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.idataerrorinfo) / [INotifyDataErrorInfo](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifydataerrorinfo).
 
### Using IDataErrorInfo
 
You can validate the data by inheriting the [IDataErrorInfo](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.idataerrorinfo) interface in model class.

{% tabs %}
{% highlight c# %}
public class OrderInfo : IDataErrorInfo 
{
    private string country;

    public string Country
    {
        get { return country; }
        set { country = value; }
    }     

    [Display(AutoGenerateField = false)]

    public string Error
    {
        get
        {
            return string.Empty;
        }
    }

    public string this[string columnName]
    {
        get 
        {

            if (!columnName.Equals("Country"))
                return string.Empty;

            if (this.Country.Contains("Germany") || this.Country.Contains("UK"))
                return "Delivery not available for the country " + this.Country;

            return string.Empty;
        }
    }        
}
{% endhighlight %}
{% endtabs %}

Enable built-in validation support by setting [SfDataGrid.GridValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridValidationMode) or [GridColumn.GridValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_GridValidationMode) property to `InEdit` or `InView`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ItemsSource="{Binding Orders}"                        
                       AllowEditing="True"                           
                       GridValidationMode="InView"/>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GridValidationMode = GridValidationMode.InView;
{% endhighlight %}
{% endtabs %}

![Data validation in WPF SfDataGrid using IDataErrorInfo](Data-Validation_images/Data-Validation_img1.png)

### INotifyDataErrorInfo

You can validate the data by inheriting the [INotifyDataErrorInfo](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifydataerrorinfo) interface in model class.

{% tabs %}
{% highlight c# %}
public class OrderInfo : INotifyDataErrorInfo
{
    private List<string> errors = new List<string>();    

    private string shippingCity;

    public string ShipCity
    {
        get { return shippingCity; }
        set { shippingCity = value; }
    }

    public System.Collections.IEnumerable GetErrors(string propertyName)
    {

        if (!propertyName.Equals("ShipCity"))
            return null;

        if (this.ShipCity.Contains("Mexico D.F."))
            errors.Add("Delivery not available for the city " + this.ShipCity);

        return errors;
    }

    [Display(AutoGenerateField = false)]

    public bool HasErrors
    {
        get
        {
            return false;
        }
    }
    public event EventHandler<DataErrorsChangedEventArgs> ErrorsChanged;
}
{% endhighlight %}
{% endtabs %}

Enable built-in validation support by setting [SfDataGrid.GridValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridValidationMode) or [GridColumn.GridValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_GridValidationMode) property to `InEdit` or `InView`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" 
                        ItemsSource="{Binding Orders}"                                                    
                        AllowEditing="True"                                                
                        GridValidationMode="InView"/>
{% endhighlight %}
{% endtabs %}

![Data validation in WPF SfDataGrid using INotifyDataErrorInfo](Data-Validation_images/Data-Validation_img2.png)

## Built-in validation using Data Annotation

You can validate the data using **data annotation attributes** by setting [SfDataGrid.GridValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridValidationMode) or [GridColumn.GridValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_GridValidationMode) property to `InEdit` or `InView`.

### Using different annotations

The numeric type like int, double, decimal properties can be validated using [Range attributes](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.rangeattribute).

{% tabs %}
{% highlight c# %}
private int orderID;
[Range(1001, 1005, ErrorMessage = "OrderID between 1001 and 1005 alone processed")]        

public int OrderID
{
    get { return orderID; }
    set { orderID = value; }
}

private decimal price;
[Range(typeof(decimal),"12","20")]

public decimal Price
{
    get { return price; }
    set { price = value; }
}
{% endhighlight %}
{% endtabs %}

The string type property can be validated using [Required](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.requiredattribute), [String Length attributes](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.stringlengthattribute)

{% tabs %}
{% highlight c# %}
private string shippingCity;
[Required]

public string ShipCity
{
    get { return shippingCity; }
    set { shippingCity = value; }
}

private string customerName;
[StringLength(17)]

public string CustomerName
{
    get { return customerName; }
    set { customerName = value; }
}
{% endhighlight %}
{% endtabs %}

The data that has heterogeneous type (combination of number, special character) can be validated using [RegularExpressions](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.regularexpressionattribute).

{% tabs %}
{% highlight c# %}
[RegularExpressionAttribute(@"^[a-zA-Z]{1,40}$", ErrorMessage="Numbers and special characters not allowed")]

public string CustomerID
{
    get { return customerId; }
    set { customerId = value; }
}
{% endhighlight %}
{% endtabs %}

## Cell validation

You can validate the cells using [CurrentCellValidating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event when the cell is edited. `CurrentCellValidating` event occurs when the edited cells tries to commit the data or lose the focus. DataGrid will not allow user to edit other cells if validation failed.

[CurrentCellValidatingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.CurrentCellValidatingEventArgs.html) provides information to `CurrentCellValidating` event for validating the cell. `CurrentCellValidatingEventArgs.OriginalSender` returns the DataGrid fired this event for DetailsView. 

`CurrentCellValidatingEventArgs.NewValue` returns the edited value and you can set the validation status using `CurrentCellValidatingEventArgs.IsValid` property.

{% tabs %}
{% highlight c# %}
this.dataGrid.CurrentCellValidating += dataGrid_CurrentCellValidating;

void dataGrid_CurrentCellValidating(object sender, CurrentCellValidatingEventArgs args)
{

    if (args.NewValue.ToString().Equals("1004"))
    {
        args.IsValid = false;
        args.ErrorMessage = "OrderID 1004 cannot be passed";
    }
}
{% endhighlight %}
{% endtabs %}

[SfDataGrid.CurrentCellValidated](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event triggered when the cell has finished validating with valid data.

{% tabs %}
{% highlight c# %}
this.dataGrid.CurrentCellValidated += dataGrid_CurrentCellValidated;

void dataGrid_CurrentCellValidated(object sender, CurrentCellValidatedEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

## Row validation

You can validate the row using [RowValidating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event when the cell is edited. The `RowValidating` event occurs when the edited cells tries to commit the row data or lose the focus. DataGrid will not allow user to edit other rows if validation failed.
 
[RowValidatingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.RowValidatingEventArgs.html) provides information to `RowValidating` event for validating row. `RowValidatingEventArgs.OriginalSender` returns the DataGrid fired this event for DetailsView. 

`RowValidatingEventArgs.RowData` returns the edited value and you can set the validation status using `RowValidatingEventArgs.IsValid` property.

{% tabs %}
{% highlight c# %}
this.dataGrid.RowValidating += dataGrid_RowValidating;

void dataGrid_RowValidating(object sender, RowValidatingEventArgs args)
{
    var data = args.RowData.GetType().GetProperty("CustomerID").GetValue(args.RowData);

    if(data.ToString().Equals("AROUT"))
    {                
        args.IsValid = false;
        args.ErrorMessages.Add("CustomerID", "Customer AROUT cannot be passed");
    }
}
{% endhighlight %}
{% endtabs %}

[SfDataGrid.RowValidated](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event triggered when the row has finished validating with valid row data.

{% tabs %}
{% highlight c# %}
this.dataGrid.RowValidated += dataGrid_RowValidated;   

void dataGrid_RowValidated(object sender, RowValidatedEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

## Data validation error icon customization

You can customize the error icon by editing `GridCell` style.

### Change the shape of error icon

You can change the validation error template shape of the GridCell by changing the `Data` property of the path in the `PART_InValidCellBorder` of GridCell.

{% tabs %}
{% highlight xaml %}
<Style TargetType="{x:Type syncfusion:GridCell}">
    <Setter Property="Background" Value="Transparent" />
    <Setter Property="BorderBrush" Value="Gray" />
    <Setter Property="BorderThickness" Value="0,0,1,1" />
    <Setter Property="Padding" Value="0,0,0,0" />
    <Setter Property="FocusVisualStyle" Value="{x:Null}" />
    <Setter Property="IsTabStop" Value="False" />
    <Setter Property="VerticalContentAlignment" Value="Center"/>
    
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:GridCell}">
                <Grid SnapsToDevicePixels="True">
                    <VisualStateManager.VisualStateGroups>
                    
                        <VisualStateGroup x:Name="IndicationStates">  
                                              
                            <VisualState x:Name="HasError">                            
                                <Storyboard>
                                    <DoubleAnimationUsingKeyFrames Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="Width">
                                        <EasingDoubleKeyFrame KeyTime="0" Value="0" />
                                        <EasingDoubleKeyFrame KeyTime="0" Value="10" />
                                    </DoubleAnimationUsingKeyFrames>
                                    <ObjectAnimationUsingKeyFrames BeginTime="00:00:00" 
                                                                   Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="(UIElement.Visibility)">
                                        <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}"/>
                                    </ObjectAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                            <VisualState x:Name="NoError">
                                <Storyboard BeginTime="0">
                                    <DoubleAnimationUsingKeyFrames Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="Width">
                                        <EasingDoubleKeyFrame KeyTime="0" Value="1" />
                                        <EasingDoubleKeyFrame KeyTime="0" Value="0" />
                                    </DoubleAnimationUsingKeyFrames>
                                    <ObjectAnimationUsingKeyFrames BeginTime="00:00:00" 
                                                                   Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="(UIElement.Visibility)">
                                        <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Collapsed}"/>
                                    </ObjectAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>  
                                                      
                        </VisualStateGroup>
                        
                        <VisualStateGroup x:Name="BorderStates">
                        
                            <VisualState x:Name="NormalCell"/>
                            
                            <VisualState x:Name="FrozenColumnCell">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
										                              Duration="1"
										                              Storyboard.TargetName="PART_GridCellBorder"
										                              Storyboard.TargetProperty="BorderThickness">
                                        <EasingThicknessKeyFrame KeyTime="0"
											Value="0,0,1,1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>                                
                            </VisualState>
                            
                            <VisualState x:Name="FooterColumnCell">                            
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
										                              Duration="1"
										                              Storyboard.TargetName="PART_GridCellBorder"
										                              Storyboard.TargetProperty="BorderThickness">
                                        <EasingThicknessKeyFrame KeyTime="0"
											                     Value="1,0,1,1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                            <VisualState x:Name="BeforeFooterColumnCell">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
										                              Duration="1"
										                              Storyboard.TargetName="PART_GridCellBorder"
										                              Storyboard.TargetProperty="BorderThickness">
                                        <EasingThicknessKeyFrame KeyTime="0"
											                     Value="0,0,0,1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                        </VisualStateGroup>
                                                
                    </VisualStateManager.VisualStateGroups>
                    
                    <Border Background="{TemplateBinding CellSelectionBrush}"
						    SnapsToDevicePixels="True"
						    Visibility="{TemplateBinding SelectionBorderVisibility}" />
                            
                    <Border x:Name="PART_GridCellBorder"
						    Background="{TemplateBinding Background}"
						    BorderBrush="{TemplateBinding BorderBrush}"
						    BorderThickness="{TemplateBinding BorderThickness}"
						    SnapsToDevicePixels="True">
                        <Grid>
                            <ContentPresenter Margin="{TemplateBinding Padding}" />
                        </Grid>
                    </Border>
                    
                    <Border Background="Transparent"
						    BorderBrush="{TemplateBinding CurrentCellBorderBrush}"
						    BorderThickness="{TemplateBinding CurrentCellBorderThickness}"
						    IsHitTestVisible="False"
						    SnapsToDevicePixels="True"
						    Margin="0,0,1,1"
						    Visibility="{TemplateBinding CurrentCellBorderVisibility}" />
                            
                    <Border x:Name="PART_InValidCellBorder"
						    Width="10"
						    Height="10"
						    HorizontalAlignment="Right"
						    Visibility="Collapsed"
						    VerticalAlignment="Top"
						    SnapsToDevicePixels="True">                            
                        <ToolTipService.ToolTip>
                            <ToolTip Background="#FFDB000C"
								     Placement="Right"
								     PlacementRectangle="20,0,0,0"
								     Tag="{TemplateBinding ErrorMessage}"
								     Template="{StaticResource ValidationToolTipTemplate}" />
                        </ToolTipService.ToolTip>                        
                        <Path Data="M15.396557,23.044006C14.220558,23.044006 13.268559,23.886993 13.268559,24.927994 13.268559,25.975006 14.220558,26.817001 15.396557,26.817001 16.572557,26.817001 17.523547,25.975006 17.523547,24.927994 17.523547,23.886993 16.572557,23.044006 15.396557,23.044006z M15.467541,5.1819992C15.447552,5.1819992 15.436566,5.1829987 15.436566,5.1829987 13.118533,5.5049973 13.055545,7.3330002 13.055545,7.3330002L13.055545,9.2929993 13.626531,16.539001C13.983558,18.357002 14.243538,19.020004 14.243538,19.020004 15.275555,19.975006 16.203567,19.25 16.203567,19.25 16.976548,18.565994 17.028552,16.962997 17.028552,16.962997 17.956563,9.2929993 17.696553,7.1029968 17.696553,7.1029968 17.608571,5.2839966 15.823561,5.1849976 15.490551,5.1819992 15.481549,5.1819992 15.473553,5.1819992 15.467541,5.1819992z M15.56355,0C15.56355,0 21.710574,4.1259995 31.581613,2.8030014 31.581613,2.8030014 33.634629,26.556992 15.56355,32 15.56355,32 -0.10249132,27.548004 0.00050565118,2.9670029 0.0005058694,2.9670029 10.72555,3.6309967 15.56355,0z"
                             Fill="Red"                                     
                             SnapsToDevicePixels="True"
                             Stretch="Fill" />                             
                    </Border>
                </Grid>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>
{% endhighlight %}
{% endtabs %}

![Data validation in WPF SfDataGrid Customizing error icon](Data-Validation_images/Data-Validation_img3.png)

### Change the color of error icon

You can change the validation error template color of the `GridCell` by changing the `Fill` property of the path in the `PART_InValidCellBorder` of `GridCell`.

{% tabs %}
{% highlight xaml %}
<Style TargetType="{x:Type syncfusion:GridCell}">
    <Setter Property="Background" Value="Transparent" />
    <Setter Property="BorderBrush" Value="Gray" />
    <Setter Property="BorderThickness" Value="0,0,1,1" />
    <Setter Property="Padding" Value="0,0,0,0" />
    <Setter Property="FocusVisualStyle" Value="{x:Null}" />
    <Setter Property="IsTabStop" Value="False" />
    <Setter Property="VerticalContentAlignment" Value="Center"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:GridCell}">
                <Grid SnapsToDevicePixels="True">
                    <VisualStateManager.VisualStateGroups>
                        <VisualStateGroup x:Name="IndicationStates">

                            <VisualState x:Name="HasError">
                                <Storyboard>
                                    <DoubleAnimationUsingKeyFrames Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="Width">
                                        <EasingDoubleKeyFrame KeyTime="0" Value="0" />
                                        <EasingDoubleKeyFrame KeyTime="0" Value="10" />
                                    </DoubleAnimationUsingKeyFrames>
                                    <ObjectAnimationUsingKeyFrames BeginTime="00:00:00" 
                                                                   Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="(UIElement.Visibility)">
                                        <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}"/>
                                    </ObjectAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>

                            <VisualState x:Name="NoError">
                                <Storyboard BeginTime="0">
                                    <DoubleAnimationUsingKeyFrames Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="Width">
                                        <EasingDoubleKeyFrame KeyTime="0" Value="1" />
                                        <EasingDoubleKeyFrame KeyTime="0" Value="0" />
                                    </DoubleAnimationUsingKeyFrames>
                                    <ObjectAnimationUsingKeyFrames BeginTime="00:00:00" 
                                                                   Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="(UIElement.Visibility)">
                                        <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Collapsed}"/>
                                    </ObjectAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                        </VisualStateGroup>
                        
                        <VisualStateGroup x:Name="BorderStates">
                            <VisualState x:Name="NormalCell"/>
                            <VisualState x:Name="FrozenColumnCell">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
										                              Duration="1"
										                              Storyboard.TargetName="PART_GridCellBorder"
										                              Storyboard.TargetProperty="BorderThickness">
                                        <EasingThicknessKeyFrame KeyTime="0"
											                     Value="0,0,1,1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                            <VisualState x:Name="FooterColumnCell">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
										                              Duration="1"
										                              Storyboard.TargetName="PART_GridCellBorder"
										                              Storyboard.TargetProperty="BorderThickness">
                                        <EasingThicknessKeyFrame KeyTime="0"
											                     Value="1,0,1,1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                            <VisualState x:Name="BeforeFooterColumnCell">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
										                              Duration="1"
										                              Storyboard.TargetName="PART_GridCellBorder"
										                              Storyboard.TargetProperty="BorderThickness">
                                        <EasingThicknessKeyFrame KeyTime="0"
											                     Value="0,0,0,1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                        </VisualStateGroup>
                        
                    </VisualStateManager.VisualStateGroups>
                    
                    <Border Background="{TemplateBinding CellSelectionBrush}"
						    SnapsToDevicePixels="True"
						    Visibility="{TemplateBinding SelectionBorderVisibility}" />

                    <Border x:Name="PART_GridCellBorder"
						    Background="{TemplateBinding Background}"
						    BorderBrush="{TemplateBinding BorderBrush}"
						    BorderThickness="{TemplateBinding BorderThickness}"
						   SnapsToDevicePixels="True">

                        <Grid>
                            <ContentPresenter Margin="{TemplateBinding Padding}" />
                        </Grid>

                    </Border>

                    <Border Background="Transparent"
						    BorderBrush="{TemplateBinding CurrentCellBorderBrush}"
						    BorderThickness="{TemplateBinding CurrentCellBorderThickness}"
						    IsHitTestVisible="False"
						    SnapsToDevicePixels="True"
						    Margin="0,0,1,1"
						    Visibility="{TemplateBinding CurrentCellBorderVisibility}" />
                    <Border x:Name="PART_InValidCellBorder"
						    Width="10"
						    Height="10"
						    HorizontalAlignment="Right"
						    Visibility="Collapsed"
						    VerticalAlignment="Top"
						    SnapsToDevicePixels="True">
                        <ToolTipService.ToolTip>
                            <ToolTip Background="#FFDB000C"
								     Placement="Right"
								     PlacementRectangle="20,0,0,0"
								     Tag="{TemplateBinding ErrorMessage}"
								     Template="{StaticResource ValidationToolTipTemplate}" />
                        </ToolTipService.ToolTip>
                        
                        <Path Data="M0.5,0.5 L12.652698,0.5 12.652698,12.068006 z"
	                          Fill="Orange"
	                          SnapsToDevicePixels="True"
	                          Stretch="Fill" />
                    </Border>
                </Grid>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>
{% endhighlight %}
{% endtabs %}

![Data validation in WPF SfDataGrid Changing color of error icon](Data-Validation_images/Data-Validation_img4.png)

### Change the cursor over error icon

You can change the validation error template cursor of the `GridCell` by changing the `Cursor` property of the path codes in the `PART_InValidCellBorder` of `GridCell`.

{% tabs %}
{% highlight xaml %}
<Style TargetType="{x:Type syncfusion:GridCell}">
    <Setter Property="Background" Value="Transparent" />
    <Setter Property="BorderBrush" Value="Gray" />
    <Setter Property="BorderThickness" Value="0,0,1,1" />
    <Setter Property="Padding" Value="0,0,0,0" />
    <Setter Property="FocusVisualStyle" Value="{x:Null}" />
    <Setter Property="IsTabStop" Value="False" />
    <Setter Property="VerticalContentAlignment" Value="Center"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:GridCell}">
                <Grid SnapsToDevicePixels="True">
                    <VisualStateManager.VisualStateGroups>
                    
                        <VisualStateGroup x:Name="IndicationStates">

                            <VisualState x:Name="HasError">
                                <Storyboard>
                                    <DoubleAnimationUsingKeyFrames Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="Width">
                                        <EasingDoubleKeyFrame KeyTime="0" Value="0" />
                                        <EasingDoubleKeyFrame KeyTime="0" Value="10" />
                                    </DoubleAnimationUsingKeyFrames>
                                    <ObjectAnimationUsingKeyFrames BeginTime="00:00:00" 
                                                                   Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="(UIElement.Visibility)">
                                        <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}"/>
                                    </ObjectAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>

                            <VisualState x:Name="NoError">
                                <Storyboard BeginTime="0">
                                    <DoubleAnimationUsingKeyFrames Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="Width">
                                        <EasingDoubleKeyFrame KeyTime="0" Value="1" />
                                        <EasingDoubleKeyFrame KeyTime="0" Value="0" />
                                    </DoubleAnimationUsingKeyFrames>
                                    <ObjectAnimationUsingKeyFrames BeginTime="00:00:00" 
                                                                   Storyboard.TargetName="PART_InValidCellBorder" 
                                                                   Storyboard.TargetProperty="(UIElement.Visibility)">
                                        <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Collapsed}"/>
                                    </ObjectAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                        </VisualStateGroup>
                        
                        <VisualStateGroup x:Name="BorderStates">
                        
                            <VisualState x:Name="NormalCell"/>
                            
                            <VisualState x:Name="FrozenColumnCell">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
										                              Duration="1"
										                              Storyboard.TargetName="PART_GridCellBorder"
										                              Storyboard.TargetProperty="BorderThickness">
                                        <EasingThicknessKeyFrame KeyTime="0"
											                     Value="0,0,1,1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                            <VisualState x:Name="FooterColumnCell">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
										                              Duration="1"
										                              Storyboard.TargetName="PART_GridCellBorder"
										                              Storyboard.TargetProperty="BorderThickness">
                                        <EasingThicknessKeyFrame KeyTime="0"
											                     Value="1,0,1,1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                            <VisualState x:Name="BeforeFooterColumnCell">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
										                              Duration="1"
										                              Storyboard.TargetName="PART_GridCellBorder"
										                              Storyboard.TargetProperty="BorderThickness">
                                        <EasingThicknessKeyFrame KeyTime="0"
											                     Value="0,0,0,1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            
                        </VisualStateGroup>
                        
                    </VisualStateManager.VisualStateGroups>
                    
                    <Border Background="{TemplateBinding CellSelectionBrush}"
						    SnapsToDevicePixels="True"
						    Visibility="{TemplateBinding SelectionBorderVisibility}" />

                    <Border x:Name="PART_GridCellBorder"
						    Background="{TemplateBinding Background}"
						    BorderBrush="{TemplateBinding BorderBrush}"
						    BorderThickness="{TemplateBinding BorderThickness}"
						    SnapsToDevicePixels="True">

                        <Grid>
                            <ContentPresenter Margin="{TemplateBinding Padding}" />
                        </Grid>

                    </Border>

                    <Border Background="Transparent"
						    BorderBrush="{TemplateBinding CurrentCellBorderBrush}"
						    BorderThickness="{TemplateBinding CurrentCellBorderThickness}"
						    IsHitTestVisible="False"
						    SnapsToDevicePixels="True"
						    Margin="0,0,1,1"
						    Visibility="{TemplateBinding CurrentCellBorderVisibility}" />
                            
                    <Border x:Name="PART_InValidCellBorder"
						    Width="10"
						    Height="10"
						    HorizontalAlignment="Right"
						    Visibility="Collapsed"
						    VerticalAlignment="Top"
						    SnapsToDevicePixels="True">
                        <ToolTipService.ToolTip>
                            <ToolTip Background="#FFDB000C"
								     Placement="Right"
								     PlacementRectangle="20,0,0,0"
								     Tag="{TemplateBinding ErrorMessage}"
								     Template="{StaticResource ValidationToolTipTemplate}" />
                        </ToolTipService.ToolTip>
                        
                        <Path Data="M0.5,0.5 L12.652698,0.5 12.652698,12.068006 z"
                              Fill="Red"
                              SnapsToDevicePixels="True"
                              Cursor="Hand"
                              Stretch="Fill" />

                    </Border>
                </Grid>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>
{% endhighlight %}
{% endtabs %}

![Data validation in WPF SfDataGrid Change the cursor on error icon](Data-Validation_images/Data-Validation_img5.png)

## Data validation error tip (help tip) customization

You can customize the error tip by editing the style of `ValidationToolTipTemplate`. Get the style of `ValidationToolTipTemplate` by editing the `GridCell` style.

### Change the background and foreground color of error tip

You can change the error tip background color by setting `Background` property of the border in `ValidationToolTipTemplate`. The error tip foreground color can be changed by setting `Foreground` property of the TextBlock in `ValidationToolTipTemplate`.

{% tabs %}
{% highlight xaml %}
<ControlTemplate x:Key="ValidationToolTipTemplate">
    <Grid x:Name="Root"
		  Margin="5,0"
		  Opacity="0"
		  RenderTransformOrigin="0,0">
        <Grid.RenderTransform>
            <TranslateTransform x:Name="xForm" X="-25" />
        </Grid.RenderTransform>
        <VisualStateManager.VisualStateGroups>
        
            <VisualStateGroup x:Name="OpenStates">
            
                <VisualStateGroup.Transitions>
                
                    <VisualTransition GeneratedDuration="0" />
                    
                    <VisualTransition GeneratedDuration="0:0:0.2" To="Open">
                        <Storyboard>
                            <DoubleAnimation Duration="0:0:0.2"
								             Storyboard.TargetName="xForm"
								             Storyboard.TargetProperty="X"
								             To="0">
                                <DoubleAnimation.EasingFunction>
                                    <BackEase Amplitude=".3" EasingMode="EaseOut" />
                                </DoubleAnimation.EasingFunction>
                            </DoubleAnimation>
                            <DoubleAnimation Duration="0:0:0.2"
								Storyboard.TargetName="Root"
								Storyboard.TargetProperty="Opacity"
								To="1" />
                        </Storyboard>
                    </VisualTransition>
                </VisualStateGroup.Transitions>
                
                <VisualState x:Name="Closed">
                    <Storyboard>
                        <DoubleAnimation Duration="0"
							             Storyboard.TargetName="Root"
							             Storyboard.TargetProperty="Opacity"
							             To="0" />
                    </Storyboard>
                </VisualState>
                
                <VisualState x:Name="Open">
                    <Storyboard>
                        <DoubleAnimation Duration="0"
							             Storyboard.TargetName="xForm"
							             Storyboard.TargetProperty="X"
							             To="0" />
                        <DoubleAnimation Duration="0"
							             Storyboard.TargetName="Root"
							             Storyboard.TargetProperty="Opacity"
							             To="1" />
                    </Storyboard>
                </VisualState>
                
            </VisualStateGroup>
            
        </VisualStateManager.VisualStateGroups>

        <Border Margin="4,4,-4,-4"
			    Background="#052A2E31"
			    CornerRadius="5" />
        <Border Margin="3,3,-3,-3"
			    Background="#152A2E31"
			    CornerRadius="4" />
        <Border Margin="2,2,-2,-2"
			    Background="#252A2E31"
			    CornerRadius="3" />
        <Border Margin="1,1,-1,-1"
			    Background="#352A2E31"
			    CornerRadius="2" />

        <Border Background="Orange" CornerRadius="2" />
        <Border CornerRadius="2">
            <TextBlock MaxWidth="250"
                       Margin="8,4,8,4"
                       Foreground="Black"
                       Text="{TemplateBinding Tag}"
                       TextWrapping="Wrap"
                       UseLayoutRounding="false" />
        </Border>
    </Grid>
</ControlTemplate>
{% endhighlight %}
{% endtabs %}

![Data validation in WPF SfDataGrid Change the background and foreground color of error tip](Data-Validation_images/Data-Validation_img6.png)

## Showing error details in RowHeader

SfDataGrid support to show the error icon in [GridRowHeaderCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridRowHeaderCell.html) based on [IDataErrorInfo.Error](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.idataerrorinfo.error) or [INotifyDataErrorInfo.HasErrors](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifydataerrorinfo.haserrors) property.

### Using IDataErrorInfo

You can show the error information in row header by setting [IDataErrorInfo.Error](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.idataerrorinfo.error). `IDataErrorInfo.Error` will be displayed as error message in tooltip.

{% tabs %}
{% highlight c# %}
[Display(AutoGenerateField = false)]

public string Error
{
    get
    {

        if (this.Country.Contains("Germany") || this.Country.Contains("UK"))
            return "Delivery not available for the country " + this.Country;

        return string.Empty;
    }
}
{% endhighlight %}
{% endtabs %}

![Data validation in WPF SfDataGrid Showing error information using IDataErrorInfo](Data-Validation_images/Data-Validation_img7.png)

### Using INotifyDataErrorInfo

You can show the error information in row header by setting [INotifyDataErrorInfo.HasErrors](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifydataerrorinfo.haserrors). By default error message **Row Containing Error** will be displayed.  You can change this by changing `RowErrorMessage` in the **resx** file.

{% tabs %}
{% highlight c# %}
[Display(AutoGenerateField = false)]

public bool HasErrors
{
    get
    {

        if (this.ShipCity.Contains("Mexico D.F."))
            return true;
        return false;
    }
}
{% endhighlight %}
{% endtabs %}

![Data validation in WPF SfDataGrid Showing error information using INotifyDataErrorInfo](Data-Validation_images/Data-Validation_img8.png)

## Data validation with Master-details view

Master-Details View allows you to [validate](#_Data_Validation) the bound data is valid or not. 
You can do both built-in and custom validation of data in `DetailsViewDataGrid`.

### Built-in validations

You can validate the bound data based on [IDataErrorInfo](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.idataerrorinfo) / [INotifyDataErrorInfo](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifydataerrorinfo) or [Data Annotation](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations) Attributes by setting [GridValidationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_GridValidationMode) property of [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid).

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                                  
                       NavigationMode="Cell"
                       AutoGenerateColumns="True"                              
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid" 
                                       GridValidationMode="InView"                                                                                         
                                       AutoGenerateColumns="True">                                                                                  
                </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

When the relation is auto-generated, the data can be validated by setting `GridValidationMode` property to `AutoGeneratingRelations.GridViewDefinition.DataGrid` in [AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler.

{% tabs %}
{% highlight c# %}
dataGrid.AutoGenerateRelations = true;

dataGrid.AutoGeneratingRelations +=dataGrid_AutoGeneratingRelations;

void dataGrid_AutoGeneratingRelations(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs e)
{
    e.GridViewDefinition.DataGrid.GridValidationMode = GridValidationMode.InView;
}
{% endhighlight %}
{% endtabs %}

![Built in Data validation in WPF SfDataGrid](Data-Validation_images/Data-Validation_img9.png)

### Custom validation through events

Master-Details View support to validate the cells and rows using [CurrentCellValidating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) and [RowValidating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) events.

#### Cell Validation

You can validate the cells using [CurrentCellValidating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event of [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) when the cell is edited. `CurrentCellValidating` event occurs when the edited cells tries to commit the data or lose the focus. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                                  
                       NavigationMode="Cell"                           
                       AutoGenerateColumns="True"                              
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"  
                                       AllowEditing="True"                                                                  CurrentCellValidating="FirstLevelNestedGrid_CurrentCellValidating"                                       
                                       AutoGenerateColumns="True">                                                                                                      
                </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

<br/>

{% tabs %}
{% highlight c# %}
this.FirstLevelNestedGrid.CurrentCellValidating +=FirstLevelNestedGrid_CurrentCellValidating;

private void FirstLevelNestedGrid_CurrentCellValidating(object sender, CurrentCellValidatingEventArgs args)
{

    if(args.NewValue.ToString().Equals("Bike2"))
    {
        args.IsValid = false;
        args.ErrorMessage = "Order ID 1002 not ordered Bike2";
    }
}
{% endhighlight %}
{% endtabs %}

[CurrentCellValidated](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) triggered when the cell has finished validating with valid data

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                                  
                       NavigationMode="Cell"                                                 
                       AutoGenerateColumns="True"                              
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"  
                                       AllowEditing="True"                                                                              CurrentCellValidated="FirstLevelNestedGrid_CurrentCellValidated"                                       
                                       AutoGenerateColumns="True">                                                                                  
                </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

<br/>

{% tabs %}
{% highlight c# %}
this.FirstLevelNestedGrid.CurrentCellValidated +=FirstLevelNestedGrid_CurrentCellValidated;

private void FirstLevelNestedGrid_CurrentCellValidated(object sender, CurrentCellValidatedEventArgs args)
{

}
{% endhighlight %}
{% endtabs %}

When the relation is auto-generated, you can wire the `CurrentCellValidating` and `CurrentCellValidated` events for `AutoGeneratingRelations.GridViewDefinition.DataGrid` in [AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler.

{% tabs %}
{% highlight c# %}
dataGrid.AutoGenerateRelations = true;
dataGrid.AutoGeneratingRelations +=dataGrid_AutoGeneratingRelations;

void dataGrid_AutoGeneratingRelations(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs e)
{
    e.GridViewDefinition.DataGrid.CurrentCellValidating += FirstLevelNestedGrid_CurrentCellValidating;
    e.GridViewDefinition.DataGrid.CurrentCellValidated += FirstLevelNestedGrid_CurrentCellValidated;
}
{% endhighlight %}
{% endtabs %}

#### Row Validation
 
You can validate the row using [RowValidating](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event of [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) when the cell is edited. 

The `RowValidating` event occurs when edited cells tries to commit the row data or lose the focus. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                                  
                       NavigationMode="Cell"
                       AutoGenerateColumns="True"                              
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"  
                                       AllowEditing="True"                                                                              RowValidating="FirstLevelNestedGrid_RowValidating"
                                       AutoGenerateColumns="True">                                                                                  
                </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}
<br/>
{% tabs %}
{% highlight c# %}
this.FirstLevelNestedGrid.RowValidating +=FirstLevelNestedGrid_RowValidating;

private void FirstLevelNestedGrid_RowValidating(object sender, RowValidatingEventArgs args)
{
    var data = args.RowData.GetType().GetProperty("ProductName").GetValue(args.RowData);

    if (data.ToString().Equals("Bike1"))
    {
        args.IsValid = false;
        args.ErrorMessages.Add("ProductName", "Product Bike 1 cannot be order for OrderID 1002");
    }
}
{% endhighlight %}
{% endtabs %}

[RowValidated](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) of [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid) event triggered when the row has finished validating with valid row data.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                                  
                       NavigationMode="Cell"
                       AutoGenerateColumns="True"                              
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="ProductDetails">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"  
                                       AllowEditing="True"                                                                                                                    
                                       RowValidated="FirstLevelNestedGrid_RowValidated"
                                       AutoGenerateColumns="True">                                                                                                  </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}
<br/>
{% tabs %}
{% highlight c# %}
this.FirstLevelNestedGrid.RowValidated +=FirstLevelNestedGrid_RowValidated;

private void FirstLevelNestedGrid_RowValidated(object sender, RowValidatedEventArgs args)
{

}
{% endhighlight %}
{% endtabs %}

When the relation is auto-generated, you can wire the `RowValidating` and `RowValidated` events for `AutoGeneratingRelations.GridViewDefinition.DataGrid` in [AutoGeneratingRelations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event handler.

{% tabs %}
{% highlight c# %}
dataGrid.AutoGenerateRelations = true;
dataGrid.AutoGeneratingRelations +=dataGrid_AutoGeneratingRelations;

void dataGrid_AutoGeneratingRelations(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingRelationsArgs e)
{
    e.GridViewDefinition.DataGrid.RowValidating += FirstLevelNestedGrid_RowValidating;
    e.GridViewDefinition.DataGrid.RowValidated += FirstLevelNestedGrid_RowValidated;
}
{% endhighlight %}
{% endtabs %}

## Data validation with checkbox column

SfDataGrid doesn’t support to validate the [GridCheckBoxColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCheckBoxColumn.html) through validating events. 

You can validate the check box column value by setting `ValidationHelper.IsCurrentCellValidated` and `ValidationHelper.IsCurrentRowValidated` static properties by calling [SetCurrentRowValidated](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ValidationHelper.html#Syncfusion_UI_Xaml_Grid_ValidationHelper_SetCurrentRowValidated_System_Boolean_) and [SetCurrentCellValidated](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ValidationHelper.html#Syncfusion_UI_Xaml_Grid_ValidationHelper_SetCurrentCellValidated_System_Boolean_) methods from [ValidationHelper](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.ValidationHelper.html).

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid.Helpers;

this.dataGrid.CurrentCellValueChanged += dataGrid_CurrentCellValueChanged;

void dataGrid_CurrentCellValueChanged(object sender, CurrentCellValueChangedEventArgs args)
{
    int columnIndex = this.dataGrid.ResolveToGridVisibleColumnIndex(args.RowColumnIndex.ColumnIndex);

    //We are enabling the RowValidating, CellValidating event if the changes happen in GridCheckBoxColumn

    if (this.dataGrid.Columns[columnIndex].CellType == "CheckBox")
    {
        this.dataGrid.GetValidationHelper().SetCurrentRowValidated(false);
        this.dataGrid.GetValidationHelper().SetCurrentCellValidated(false);
    }
}
{% endhighlight %}
{% endtabs %}

![Data validation in WPF SfDataGrid Validation with Checkbox column](Data-Validation_images/Data-Validation_img10.png)

## Show validation errors when using UseDrawing

By default, validation is not supported while enabling the `UseDrawing` property since the cell content were drawn instead of loading the UIElement. However, SfDataGrid provides an option to achieve the validation by adding the validation template. 

Please refer the below code example for further details about achieving Validation when using `UseDrawing` property.
{% tabs %}
{% highlight xaml %}
<Window.Resources>
        <ControlTemplate x:Key="ValidationToolTipTemplate">
            <Grid x:Name="Root"
              Margin="5,0"
              Opacity="0"
              RenderTransformOrigin="0,0">
                <Grid.RenderTransform>
                    <TranslateTransform x:Name="xform" X="-25" />
                </Grid.RenderTransform>
                <VisualStateManager.VisualStateGroups>
                    <VisualStateGroup Name="OpenStates">
                        <VisualStateGroup.Transitions>
                            <VisualTransition GeneratedDuration="0" />
                            <VisualTransition GeneratedDuration="0:0:0.2" To="Open">
                                <Storyboard>
                                    <DoubleAnimation Duration="0:0:0.2"
                                                 Storyboard.TargetName="xform"
                                                 Storyboard.TargetProperty="X"
                                                 To="0">
                                        <DoubleAnimation.EasingFunction>
                                            <BackEase Amplitude=".3" EasingMode="EaseOut" />
                                        </DoubleAnimation.EasingFunction>
                                    </DoubleAnimation>
                                    <DoubleAnimation Duration="0:0:0.2"
                                                 Storyboard.TargetName="Root"
                                                 Storyboard.TargetProperty="Opacity"
                                                 To="1" />
                                </Storyboard>
                            </VisualTransition>
                        </VisualStateGroup.Transitions>
                        <VisualState x:Name="Closed">
                            <Storyboard>
                                <DoubleAnimation Duration="0"
                                             Storyboard.TargetName="Root"
                                             Storyboard.TargetProperty="Opacity"
                                             To="0" />
                            </Storyboard>
                        </VisualState>
                        <VisualState x:Name="Open">
                            <Storyboard>
                                <DoubleAnimation Duration="0"
                                             Storyboard.TargetName="xform"
                                             Storyboard.TargetProperty="X"
                                             To="0" />
                                <DoubleAnimation Duration="0"
                                             Storyboard.TargetName="Root"
                                             Storyboard.TargetProperty="Opacity"
                                             To="1" />
                            </Storyboard>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateManager.VisualStateGroups>

                <Border Margin="4,4,-4,-4"
                    Background="#052A2E31"
                    CornerRadius="5" />
                <Border Margin="3,3,-3,-3"
                    Background="#152A2E31"
                    CornerRadius="4" />
                <Border Margin="2,2,-2,-2"
                    Background="#252A2E31"
                    CornerRadius="3" />
                <Border Margin="1,1,-1,-1"
                    Background="#352A2E31"
                    CornerRadius="2" />

                <Border Background="#FFDC000C" CornerRadius="2" />
                <Border CornerRadius="2">
                    <TextBlock MaxWidth="250"
                           Margin="8,4,8,4"
                           Foreground="White"
                           Text="{TemplateBinding Tag}"
                           TextWrapping="Wrap"
                           UseLayoutRounding="false" />
                </Border>
            </Grid>
        </ControlTemplate>
        <ControlTemplate x:Key="GridCellControlTemplate" TargetType="Syncfusion:GridCell">
            <Grid SnapsToDevicePixels="True">
                <VisualStateManager.VisualStateGroups>
                    <VisualStateGroup x:Name="IndicationStates">
                        <VisualState x:Name="NoError">
                            <Storyboard BeginTime="0">
                                <!--<DoubleAnimationUsingKeyFrames Storyboard.TargetName="PART_InValidCellBorder" Storyboard.TargetProperty="Width">
                                            <EasingDoubleKeyFrame KeyTime="0" Value="1" />
                                            <EasingDoubleKeyFrame KeyTime="0" Value="0" />
                                        </DoubleAnimationUsingKeyFrames>-->
                                <ObjectAnimationUsingKeyFrames BeginTime="00:00:00"
                                                                       Storyboard.TargetName="PART_InValidCellBorder"
                                                                       Storyboard.TargetProperty="(UIElement.Visibility)">
                                    <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Collapsed}" />
                                </ObjectAnimationUsingKeyFrames>
                            </Storyboard>
                        </VisualState>
                        <VisualState x:Name="HasError">
                            <Storyboard>
                                <!--<DoubleAnimationUsingKeyFrames Storyboard.TargetName="PART_InValidCellBorder" Storyboard.TargetProperty="Width">
                                            <EasingDoubleKeyFrame KeyTime="0" Value="0" />
                                            <EasingDoubleKeyFrame KeyTime="0" Value="10" />
                                        </DoubleAnimationUsingKeyFrames>-->
                                <ObjectAnimationUsingKeyFrames BeginTime="00:00:00"
                                                                       Storyboard.TargetName="PART_InValidCellBorder"
                                                                       Storyboard.TargetProperty="(UIElement.Visibility)">
                                    <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}" />
                                </ObjectAnimationUsingKeyFrames>
                            </Storyboard>
                        </VisualState>

                    </VisualStateGroup>
                    <VisualStateGroup x:Name="BorderStates">
                        <VisualState x:Name="NormalCell" />
                        <VisualState x:Name="FrozenColumnCell"/>
                        <VisualState x:Name="FooterColumnCell">
                            <Storyboard BeginTime="0">
                                <ThicknessAnimationUsingKeyFrames BeginTime="0"
                                                                          Duration="1"
                                                                          Storyboard.TargetName="PART_GridCellBorder"
                                                                          Storyboard.TargetProperty="BorderThickness">
                                    <EasingThicknessKeyFrame KeyTime="0" Value="1,0,1,1" />
                                </ThicknessAnimationUsingKeyFrames>
                            </Storyboard>
                        </VisualState>
                        <VisualState x:Name="BeforeFooterColumnCell">
                            <Storyboard BeginTime="0">
                                <ThicknessAnimationUsingKeyFrames BeginTime="0"
                                                                          Duration="1"
                                                                          Storyboard.TargetName="PART_GridCellBorder"
                                                                          Storyboard.TargetProperty="BorderThickness">
                                    <EasingThicknessKeyFrame KeyTime="0" Value="0,0,0,1" />
                                </ThicknessAnimationUsingKeyFrames>
                            </Storyboard>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateManager.VisualStateGroups>
                <Border Background="{TemplateBinding CellSelectionBrush}"
                                SnapsToDevicePixels="True"
                                Visibility="{TemplateBinding SelectionBorderVisibility}" />

                <Border x:Name="PART_GridCellBorder"
                                Background="{TemplateBinding Background}"
                                BorderBrush="{TemplateBinding BorderBrush}"
                                BorderThickness="{TemplateBinding BorderThickness}"
                                SnapsToDevicePixels="True">
                    <ContentPresenter Margin="{TemplateBinding Padding}" Opacity="{TemplateBinding AnimationOpacity}" />
                </Border>

                <Border Margin="0,0,1,1"
                                Background="Transparent"
                                BorderBrush="{TemplateBinding CurrentCellBorderBrush}"
                                BorderThickness="{TemplateBinding CurrentCellBorderThickness}"
                                IsHitTestVisible="False"
                                SnapsToDevicePixels="True"
                                Visibility="{TemplateBinding CurrentCellBorderVisibility}" />
                <Border x:Name="PART_InValidCellBorder"
                                Width="10"
                                Height="10"
                                HorizontalAlignment="Right"
                                VerticalAlignment="Top"
                                SnapsToDevicePixels="True"
                                Visibility="Collapsed">
                    <ToolTipService.ToolTip>
                        <ToolTip Background="#FFDB000C"
                                         Placement="Right"
                                         PlacementRectangle="20,0,0,0"
                                         Tag="{TemplateBinding ErrorMessage}"
                                         Template="{StaticResource ValidationToolTipTemplate}" />
                    </ToolTipService.ToolTip>
                    <Path Data="M0.5,0.5 L12.652698,0.5 12.652698,12.068006 z"
                                  Fill="Red"
                                  SnapsToDevicePixels="True"
                                  Stretch="Fill" />
                </Border>
            </Grid>
        </ControlTemplate>
        <Style TargetType="Syncfusion:GridHeaderCellControl">
            <Setter Property="BorderThickness" Value="0.4"/>
        </Style>
        <Style TargetType="Syncfusion:GridCell">
            <Setter Property="BorderThickness" Value="0.4"/>
            <Setter Property="Template" Value="{StaticResource GridCellControlTemplate}"/>
        </Style>
    </Window.Resources>
{% endhighlight %}
{% endtabs %}

You can download a working demo for the above customization from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/WPF1707875331). 

## Limitations
 
1. Non editable columns will not support custom validation except [GridCheckBoxColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCheckBoxColumn.html).
2. `CurrentCellValidating` event will not triggered for [GridTemplateColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridTemplateColumn.html) and [GridUnboundColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnBoundColumn.html). 

## See Also

[How to navigate to the error cells in datagrid via button click?](https://www.syncfusion.com/kb/9600)

[How to validate the AddNewRow value based on already existing records?](https://www.syncfusion.com/kb/6596)

[How to show the validation tooltip without hovering the red indicator in cell?](https://www.syncfusion.com/kb/6234)

[How to fire RowValidating event for GridCheckBoxColumn in SfDataGrid](https://www.syncfusion.com/kb/5954)

[How to remove the top-right corner error mark from the GridCell by pressing Esc key when validated by handling the CurrentCellValidating event?](https://www.syncfusion.com/kb/5317)

[How to change the validation error template color?](https://www.syncfusion.com/kb/2574)

[How to wire the RowValidating event after pasted the content to datagrid?](https://www.syncfusion.com/kb/9432)
