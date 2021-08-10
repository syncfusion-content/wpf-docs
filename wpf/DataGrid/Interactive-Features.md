---
layout: post
title: Interactive Features in WPF DataGrid control | Syncfusion
description: Learn here all about Interactive Features support in Syncfusion WPF DataGrid (SfDataGrid) control and more.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Interactive Features in WPF DataGrid (SfDataGrid)

## Column Chooser

SfDataGrid allows you to show and hide the Columns from the view at runtime via drag and drop using `ColumnChooser`. You can enable a column chooser in an application by creating an instance for `GridColumnChooserController` and assign to `SfDataGrid.GridColumnDragDropController`.

While dropping columns in `ColumnChooser` window, the particular column will be hidden by setting `GridColumn.IsHidden` as `true`.

{% tabs %}
{% highlight c# %}

ColumnChooser chooserWindow;

void MainWindow_Loaded(object sender, RoutedEventArgs e)
{
    chooserWindow = new ColumnChooser(this.dataGrid);
    chooserWindow.Resources.MergedDictionaries.Clear();
    chooserWindow.ClearValue(ColumnChooser.StyleProperty);

    //Resources has been added to the Merged Dictionaries     
    chooserWindow.Resources.MergedDictionaries.Add(this.MainGrid.Resources.MergedDictionaries[0]);
    this.dataGrid.GridColumnDragDropController = new GridColumnChooserController(this.dataGrid, chooserWindow);

    //ColumnChooser Window will open
    chooserWindow.Show();
    chooserWindow.Owner = this;
}

{% endhighlight %}
{% endtabs %}

![WPF DataGrid displays Column Chooser](Interactive-Features_images/wpf-datagrid-column-chooser.png)

### Custom Column Chooser

You can create custom UI for the column chooser and you can enable this view manually like below code example. You need to maintain separate collection in `ViewModel` to maintain the hidden columns which will bound to custom view.

{% tabs %}
{% highlight xaml %}

<syncfusion:ChromelessWindow >    
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="*" />
            <RowDefinition Height="50" />
        </Grid.RowDefinitions>
        <ListBox x:Name="listBox"
                 Grid.Row="0"
                 Margin="0,5"
                 HorizontalAlignment="Stretch"
                 BorderThickness="0"
                 ItemContainerStyle="{StaticResource ListBoxItemStyle1}"
                 ItemsSource="{Binding ColumnCollection}">
            <ListBox.ItemTemplate>
                <StaticResource ResourceKey="MyDataTemplate" />
            </ListBox.ItemTemplate>
        </ListBox>
        <StackPanel Grid.Row="1" Margin="20,0,0,0"
                    VerticalAlignment="Stretch"
                    Background="Transparent"
                    Orientation="Horizontal">
            <Button Margin="5"
                    Click="OKButton_Click"
                    Content="OK"
                    Style="{StaticResource ButtonStyle}" />
            <Button Margin="5"
                    Content="Cancel"
                    IsCancel="True"
                    Style="{StaticResource ButtonStyle}" />
        </StackPanel>
    </Grid>
    <syncfusion:ChromelessWindow.Resources>
        <Style x:Key="FocusVisual">
            <Setter Property="Control.Template">
                <Setter.Value>
                    <ControlTemplate>
                        <Rectangle Margin="2"
                                   SnapsToDevicePixels="true"
                                   Stroke="{DynamicResource {x:Static SystemColors.ControlTextBrushKey}}"
                                   StrokeDashArray="1 2"
                                   StrokeThickness="1" />
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>
        <SolidColorBrush x:Key="Item.MouseOver.Background" Color="#1F26A0DA" />
        <SolidColorBrush x:Key="Item.MouseOver.Border" Color="#a826A0Da" />
        <SolidColorBrush x:Key="Item.SelectedInactive.Background" Color="#3DDADADA" />
        <SolidColorBrush x:Key="Item.SelectedInactive.Border" Color="#FFDADADA" />
        <SolidColorBrush x:Key="Item.SelectedActive.Background" Color="#3D26A0DA" />
        <SolidColorBrush x:Key="Item.SelectedActive.Border" Color="#FF26A0DA" />
        
        //ListBoxItem is Customized through the DataTemplate
        <Style x:Key="ListBoxItemStyle1" TargetType="ListBoxItem">
            <Setter Property="SnapsToDevicePixels" Value="True" />
            <Setter Property="Padding" Value="4,1" />
            <Setter Property="HorizontalContentAlignment" Value="{Binding HorizontalContentAlignment, RelativeSource={RelativeSource AncestorType={x:Type ItemsControl}}}" />
            <Setter Property="VerticalContentAlignment" Value="{Binding VerticalContentAlignment, RelativeSource={RelativeSource AncestorType={x:Type ItemsControl}}}" />
            <Setter Property="Background" Value="Transparent" />
            <Setter Property="BorderBrush" Value="Transparent" />
            <Setter Property="BorderThickness" Value="1" />
            <Setter Property="FocusVisualStyle" Value="{StaticResource FocusVisual}" />
                <DataTemplate x:Key="MyDataTemplate">
                    <Grid Margin="0,3,0,3">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="Auto" />
                            <ColumnDefinition Width="Auto" />
                        </Grid.ColumnDefinitions>
                        <CheckBox Margin="0,2,0,0"
                                  HorizontalAlignment="Center"
                                  VerticalAlignment="Center"
                                  IsChecked="{Binding IsChecked,Mode=TwoWay}"
                                  Padding="2,0,0,0">
                        </CheckBox>
                        <TextBlock Grid.Column="1"
                                   HorizontalAlignment="Left"
                                   VerticalAlignment="Center"
                                   FontFamily="Segoe UI"
                                   FontSize="14"
                                   Padding="10,0,0,0"
                                   Text="{Binding Name}" />
                    </Grid>
                </DataTemplate>
                
            //Customizing the Button by using the VisualState
                <Style x:Key="ButtonStyle" TargetType="Button">
                    <Setter Property="Template">
                        <Setter.Value>
                            <ControlTemplate TargetType="Button">
                                <Grid>
                                    <VisualStateManager.VisualStateGroups>
                                        <VisualStateGroup x:Name="CommonStates">
                                            <VisualState x:Name="Normal" />
                                            <VisualState x:Name="MouseOver" />
                                            <VisualState x:Name="Pressed">
                                                <Storyboard>
                                                    <ColorAnimationUsingKeyFrames Storyboard.TargetName="textBlock" Storyboard.TargetProperty="(TextElement.Foreground).(SolidColorBrush.Color)">
                                                        <EasingColorKeyFrame KeyTime="0" Value="White" />
                                                    </ColorAnimationUsingKeyFrames>
                                                    <ColorAnimationUsingKeyFrames Storyboard.TargetName="border" Storyboard.TargetProperty="(Panel.Background).(SolidColorBrush.Color)">
                                                        <EasingColorKeyFrame KeyTime="0" Value="#FF55C5D5" />
                                                    </ColorAnimationUsingKeyFrames>
                                                </Storyboard>
                                            </VisualState>
                                        <VisualState x:Name="Disabled" />
                                    </VisualStateGroup>
                                 </VisualStateManager.VisualStateGroups>
                                <Border x:Name="border"
                                        Width="80"
                                        Height="24"
                                        Background="Gray">
                                <TextBlock x:Name="textBlock"
                                           HorizontalAlignment="Center"
                                           VerticalAlignment="Center"
                                           FontSize="14"
                                           Foreground="White"
                                           Text="{TemplateBinding Content}" />
                            </Border>
                        </Grid>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:ChromelessWindow.Resources>
</syncfusion:ChromelessWindow>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

var visibleColumns = this.AssociatedObject.dataGrid.Columns;
ObservableCollection<ColumnChooserItems> totalColumns = GetColumnsDetails(visibleColumns);
CustomColumnChooserViewModel chooserViewModel = new CustomColumnChooserViewModel(totalColumns);
CustomColumnChooser ColumnChooserView = new CustomColumnChooser(chooserViewModel);
ColumnChooserView.Owner = Application.Current.MainWindow;
chooserWindow.Visibility = System.Windows.Visibility.Collapsed;

if ((bool)ColumnChooserView.ShowDialog())
    ClickOKButton(chooserViewModel.ColumnCollection, this.AssociatedObject.dataGrid);
viewModel.ShowColumnChooser = false;

//This will add or remove the Columns from the SfDataGrid

public void ClickOKButton(ObservableCollection<ColumnChooserItems> ColumnCollection, SfDataGrid dataGrid)
{

    foreach (var item in ColumnCollection)
    {
        var column = dataGrid.Columns.FirstOrDefault(v => v.MappingName == item.Name);

        if (column != null)
        {

            if (item.IsChecked == false && !column.IsHidden)
            column.IsHidden = true;

            else if (item.IsChecked == true && column.IsHidden == true)
            {

                if (column.Width == 0)
                    column.Width = 150;
                column.IsHidden = false;
            }
        }
    }
viewModel.ShowColumnChooser = false;
}

{% endhighlight %}
{% endtabs %}

![Customizing Column Chooser in WPF DataGrid](Interactive-Features_images/wpf-datagrid-column-chooser-customization.png)


### Appearance Customization

You can change the default appearance of the column chooser window by customizing the style of `ColumnChooser`. You can directly change the `Title` and `WaterMarkText` like the below code example.

{% tabs %}
{% highlight c# %}

ColumnChooser chooserWindow;

void MainWindow_Loaded(object sender, RoutedEventArgs e)
{
    chooserWindow = new ColumnChooser(this.dataGrid);
    chooserWindow.Resources.MergedDictionaries.Clear();
    chooserWindow.ClearValue(ColumnChooser.StyleProperty);            
    chooserWindow.Resources.MergedDictionaries.Add(this.MainGrid.Resources.MergedDictionaries[0]);
    this.dataGrid.GridColumnDragDropController = new GridColumnChooserController(this.dataGrid, chooserWindow);
    chooserWindow.Title = "Columns";
    chooserWindow.WaterMarkText = "Drag the columns";
    chooserWindow.Show();
    chooserWindow.Owner = this;
}

{% endhighlight %}
{% endtabs %}

![Customizing Column Chooser Appearance in wpf datagrid](Interactive-Features_images/wpf-datagrid-column-chooser-customization.png)


