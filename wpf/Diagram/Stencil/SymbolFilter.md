---
layout: post
title: Symbol fillters of stencil in WPF Diagram control | Syncfusion
description: Learn here all about symbol filtering and appearance of symbol filtering support of stencil in Syncfusion WPF Diagram (SfDiagram).
platform: wpf
control: SfDiagram
documentation: ug
---

# Symbol filtering of Stencil in WPF Diagram (SfDiagram)

The grouped symbols can be filtered or hide using the [SymbolFilters](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolFilters). The `SymbolFilters` are a collection of [SymbolFilterProvider](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html) which contains the [SymbolFilter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolFilterProvider_SymbolFilter) delegate property to filter the specific symbol group.

The [Content](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolFilterProvider_Content) and [ContentTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolFilterProvider_ContentTemplate) property of the `SymbolFilterProvider` is used to update the content of the symbol filter.

The following code explains how to create a symbol filter in the stencil.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
   <viewmodel:StencilVM></viewmodel:StencilVM>
</Window.DataContext>
<Window.Resources>
<DataTemplate x:Key="TitleTemplate">
   <TextBlock x:Name="HeaderText" Text="{Binding}" FontSize="15" FontWeight="SemiBold"  Foreground="#2b579a" >
   </TextBlock>
</DataTemplate>
<!--Style for Node-->
<Style TargetType="{x:Type syncfusion:Node}">
    <Setter Property="ShapeStyle">
     <Setter.Value>
       <Style  TargetType="Path">
         <Setter Property="Fill" Value="#FF5B9BD5"/>
         <Setter Property="Stroke" Value="#FFEDF1F6"/>
         <Setter Property="StrokeThickness" Value="1"/>
         <Setter Property="Stretch" Value="Fill"/>
       </Style>
     </Setter.Value>
    </Setter>
</Style>
<!--Style for Connector-->
<Style TargetType="{x:Type syncfusion:Connector}">
   <Setter Property="ConnectorGeometryStyle">
    <Setter.Value>
      <Style TargetType="Path">
        <Setter Property="Stroke" Value="#FF5B9BD5"></Setter>
        <Setter Property="StrokeThickness" Value="1"></Setter>
      </Style>
    </Setter.Value>
   </Setter>
   <Setter Property="TargetDecoratorStyle">
    <Setter.Value>
      <Style TargetType="Path">
        <Setter Property="Fill" Value="#FF5B9BD5"></Setter>
        <Setter Property="StrokeThickness" Value="1"></Setter>
      </Style>
    </Setter.Value>
   </Setter>
</Style>
<!--Style for Symbol-->
<Style TargetType="stencil:Symbol">
  <Setter Property="Width" Value="100" />
  <Setter Property="Height" Value="100" />
  <Setter Property="BorderThickness" Value="1" />
  <Setter Property="Background" Value="Transparent" />
  <Setter Property="BorderBrush" Value="Transparent" />
  <Setter Property="Margin" Value="4"></Setter>
</Style>
<!--Style for Symbol Group-->
<Style TargetType="stencil:SymbolGroup">
  <Setter Property="FontFamily" Value="Regular"/>
  <Setter Property="Background" Value="#ffffff"/>
  <Setter Property="Foreground" Value="#222222"/>
  <Setter Property="FontSize" Value="14"/>
  <Setter Property="HeaderTemplate">
    <Setter.Value>
      <DataTemplate>
        <stencil:Header>
          <stencil:Header.Template>
            <ControlTemplate TargetType="stencil:Header">
              <Grid>
                <Border x:Name="header" Background="#f5f5f5" BorderBrush="#dfdfdf" BorderThickness="1">
                  <ContentPresenter Margin="10" Content="{Binding}"/>
                </Border>
               </Grid>
            </ControlTemplate>
          </stencil:Header.Template>
        </stencil:Header>
      </DataTemplate>
    </Setter.Value>
  </Setter>
</Style>
</Window.Resources>
<Grid>
  <Grid.ColumnDefinitions>
    <ColumnDefinition Width="2*"/>
    <ColumnDefinition Width="8*"/>
  </Grid.ColumnDefinitions>
  <!--Define the Stencil-->
   <stencil:Stencil Grid.Column="0" BorderThickness="1" BorderBrush="#dfdfdf" Title="Shapes" TitleTemplate="{StaticResource TitleTemplate}"  x:Name="stencil" ExpandMode="All" SymbolFilters="{Binding Symbolfilters}" SelectedFilter="{Binding Selectedfilter}">
     <!--Initialize the SymbolSource-->
     <stencil:Stencil.SymbolSource>
      <!--Initialize the SymbolCollection-->
      <local:SymbolCollection>
       <!--Define the DiagramElement-Node-->
        <syncfusion:NodeViewModel x:Name="node" UnitHeight="100" UnitWidth="100" OffsetX="100" OffsetY="100" Shape="{StaticResource Rectangle}" Key="Nodes">
          </syncfusion:NodeViewModel>
       <!--Define the DiagramElement- Connector-->
         <syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="200,200" Key="Connector">
          </syncfusion:ConnectorViewModel>
      </local:SymbolCollection>
      </stencil:Stencil.SymbolSource>
       <!--Initialize the SymbolGroup-->
       <stencil:Stencil.SymbolGroups>
        <stencil:SymbolGroups>
         <!--Map Symbols Using MappingName-->
         <stencil:SymbolGroupProvider MappingName="Key"></stencil:SymbolGroupProvider>
        </stencil:SymbolGroups>
       </stencil:Stencil.SymbolGroups>
     </stencil:Stencil>
</Grid>
{% endhighlight %}
{% highlight C# %}

public class StencilVM : INotifyPropertyChanged
{
   public StencilVM()
   {
     Symbolfilters = new SymbolFilters();
     SymbolFilterProvider all = new SymbolFilterProvider { Content = "All",  SymbolFilter = Filter };
     SymbolFilterProvider Node = new SymbolFilterProvider { Content = "Nodes", SymbolFilter = Filter };
     SymbolFilterProvider Con = new SymbolFilterProvider { Content = "Connector", SymbolFilter = Filter };

      this.Symbolfilters.Add(all);
      this.Symbolfilters.Add(Node);
      this.Symbolfilters.Add(Con);
      this.Selectedfilter = Symbolfilters[0];
   }

   // Define the filtering of symbols.
   private bool Filter(SymbolFilterProvider sender, object symbol)
   {
      if (symbol is NodeViewModel)
       {
         if (sender.Content.ToString() == (symbol as NodeViewModel).Key.ToString())
             return true;
       }

       if (symbol is ConnectorViewModel)
       {
        if (sender.Content.ToString() == (symbol as ConnectorViewModel).Key.ToString())
               return true;
        }
        if (sender.Content.ToString() == "All")
        {
          return true;
        }
        return false;
    }
   public ObservableCollection<SymbolFilterProvider> Symbolfilters { get; set; } 

   public SymbolFilterProvider Selectedfilter { get; set; }

   public event PropertyChangedEventHandler PropertyChanged;
}
{% endhighlight %}
{% endtabs %}

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/SymbolFilters-sample)

![SymbolFilter](Stencil_images/Stencil_img12.PNG)

## Appearance of symbol filters

The visual appearance of the symbol filters can be customized to either a combo box or list view. The [SymbolFilterDisplayMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolFilterDisplayMode) property of the `Stencil` is used to customize the appearance of the symbol filter.

|SymbolFilterDisplayMode|Description|
|----------|-----------|
| ComboBox | The symbol filter is visually represented in a combo box.  |
| List | The symbol filter are visually represented in a listview |

In `List` display mode,  the filters will be added in the list view only when you set the [IsChecked](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolFilterProvider_IsChecked) property of the `SymbolFilterProvider` to `true.` You can dynamically add or remove the filter from the list view, by clicking the **more shapes** option and checked or unchecked the filter to add or remove that filter from the list view.  Check marks indicate the filters added to the List.

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil_ListView)

 ![Symbol](Stencil_images/StencilImprovement.GIF) 

### SelectedFilter

There can be multiple SymbolFilters but only one filter can be selected at a time. You can select the filter from the collection of filters using the [SelectedFilter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SelectedFilter) of the stencil. In the combo box, a particular item will be selected and updated that item to the SelectedFilter. In List view, the selected item will be updated as a SelectedFilter.
