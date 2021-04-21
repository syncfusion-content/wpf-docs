---
layout: post
title: Node CheckBox in SfTreeGrid
description: Node CheckBox support in SfTreeGrid
platform: wpf
control: SfTreeGrid
documentation: ug
---
# Node Checkbox

SfTreeGrid provides support for loading `CheckBox` in the expander cell of each node, which allows the user to check/uncheck the corresponding node. You can display check box in each node by setting [SfTreeGrid.ShowCheckBox](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ShowCheckBox) property as `true`. It also provides support to process the selection in the context of state of the checkbox based on [SfTreeGrid.CheckBoxSelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CheckBoxSelectionMode) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       ChildPropertyName="Children"
                       ItemsSource="{Binding PersonDetails}"
                       CheckBoxSelectionMode="Default"
                       ShowCheckBox="True"/>
{% endhighlight %}
{% highlight c# %}
treeGrid.ShowCheckBox = true;
treeGrid.CheckBoxSelectionMode = CheckBoxSelectionMode.Default;
{% endhighlight %}
{% endtabs %}

![WPF SfTreeGrid Node-CheckBox Image1](Node-CheckBox_images/Node-CheckBox_img1.png)

## Indeterminate State Support

You can enable or disable the indeterminate state for node CheckBox using [SfTreeGrid.AllowTriStateChecking](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_AllowTriStateChecking) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       AllowTriStateChecking="True"
                       ChildPropertyName="Children"
                       ItemsSource="{Binding PersonDetails}"
                       ShowCheckBox="True"/>
{% endhighlight %}
{% highlight c# %}
treeGrid.AllowTriStateChecking = true;
{% endhighlight %}
{% endtabs %}

## Recursive Checking

SfTreeGrid provides support for recursive checking where the checked state of parent node and child nodes is changed recursively based on the state of currently changed node. You can enable recursive checking by setting [SfTreeGrid.EnableRecursiveChecking](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_EnableRecursiveChecking) property as `true`.

* A tree node will be checked only if all its child nodes are checked.
* A tree node will be unchecked if all its child nodes are unchecked. 
* The tree node will be in Indeterminate state in other combinations of its children.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       EnableRecursiveChecking="True"
                       ChildPropertyName="Children"
                       ItemsSource="{Binding PersonDetails}"
                       ShowCheckBox="True"/>
{% endhighlight %}
{% highlight c# %}
treeGrid.EnableRecursiveChecking = true;
{% endhighlight %}
{% endtabs %}

![WPF SfTreeGrid Node-CheckBox Image2](Node-CheckBox_images/Node-CheckBox_img2.png)

N> Even though [SfTreeGrid.AllowTriStateChecking](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_AllowTriStateChecking) is `false` if [SfTreeGrid.EnableRecursiveChecking](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_EnableRecursiveChecking) is `true`, CheckBox can be in indeterminate state.

## Saving and loading Node CheckBox state from the property in data object

You can bind state of node checkbox to the bool property in underlying data object by using [SfTreeGrid.CheckBoxMappingName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CheckBoxMappingName) property. TreeGrid updates the checked state of checkbox when underlying data object property gets changed and vice versa.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       CheckBoxMappingName="IsSelected"
                       ChildPropertyName="Children"
                       ItemsSource="{Binding PersonDetails}"
                       ShowCheckBox="True"/>
{% endhighlight %}
{% highlight c# %}
treeGrid.CheckBoxMappingName = "IsSelected";
{% endhighlight %}
{% endtabs %}

### Disable Recursive Checking when data object property changed

By default, recursive checking will be applied, whenever node’s `IsChecked` property gets changed. You can disable the recursive checking on property value change (which is mapped with `CheckBoxMappingName`) by setting [SfTreeGrid.RecursiveCheckingMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_RecursiveCheckingMode) as `OnCheck`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       EnableRecursiveChecking="True"
                       ChildPropertyName="Children"
                       RecursiveCheckingMode="OnCheck"
                       ItemsSource="{Binding PersonDetails}"
                       ShowCheckBox="True"/>
{% endhighlight %}
{% highlight c# %}
treeGrid.RecursiveCheckingMode = RecursiveCheckingMode.OnCheck;
{% endhighlight %}
{% endtabs %}

## Disabling CheckBox for certain nodes

You can disable CheckBox by writing style for [TreeGridExpanderCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridExpanderCell.html) and setting [IsCheckBoxEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridExpanderCell.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridExpanderCell_IsCheckBoxEnabled) property as ‘false’

{% tabs %}
{% highlight xaml %}
<Style TargetType="syncfusion:TreeGridExpanderCell">
            <Setter Property="IsCheckBoxEnabled" Value="{Binding Path=HasChildNodes, RelativeSource={RelativeSource Self}}" />
</Style>
{% endhighlight %}
{% endtabs %}

In the below screenshot, node CheckBox is disabled for leaf nodes.

![WPF SfTreeGrid Node-CheckBox Image3](Node-CheckBox_images/Node-CheckBox_img3.png)

## Collapsing CheckBox for certain nodes

You can collapse node CheckBox for certain nodes by editing the control template of [TreeGridExpanderCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridExpanderCell.html) and changing the Checkbox visibility based on condition.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="/Syncfusion.SfGrid.WPF;component/Control/Themes/Generic.xaml" />
            </ResourceDictionary.MergedDictionaries>
            <local:BoolToVisibilityConverter x:Key="boolToVisibilityConverter" />
            <Style TargetType="syncfusion:TreeGridExpanderCell">
                <Setter Property="Background" Value="Transparent" />
                <Setter Property="BorderThickness" Value="0,0,1,1" />
                <Setter Property="BorderBrush" Value="Gray" />
                <Setter Property="Padding" Value="0" />
                <Setter Property="Template">
                    <Setter.Value>
                        <ControlTemplate TargetType="syncfusion:TreeGridExpanderCell">
                            <Grid x:Name="Root">
                                <Border x:Name="PART_GridCellBorder"
                                        Background="{TemplateBinding Background}"
                                        BorderBrush="{TemplateBinding BorderBrush}"
                                        BorderThickness="{TemplateBinding BorderThickness}"
                                        SnapsToDevicePixels="True">
                                    <Grid Margin="{TemplateBinding IndentMargin}">
                                        <Grid.ColumnDefinitions>
                                            <ColumnDefinition Width="14" />
                                            <ColumnDefinition Width="Auto" />
                                            <ColumnDefinition Width="*" />
                                        </Grid.ColumnDefinitions>
                                        <syncfusion:TreeGridExpander x:Name="PART_ExpanderCell"
                                                                     Grid.Column="0"
                                                                     Width="12"
                                                                     Height="12"
                                                                     Margin="2,1,0,1"
                                                                     HorizontalAlignment="Center"
                                                                     VerticalAlignment="Center"
                                                                     IsExpanded="{Binding RelativeSource={RelativeSource TemplatedParent},
                                                                                          Path=IsExpanded,
                                                                                          Mode=TwoWay}"
                                                                     Visibility="{Binding RelativeSource={RelativeSource TemplatedParent},
                                                                                          Path=HasChildNodes,
                                                                                          Converter={StaticResource boolToVisibilityConverter},
                                                                                          Mode=TwoWay}" />

                                        <CheckBox Name="PART_SelectCheckBox"
                                                  Grid.Column="1"
                                                  Width="16"
                                                  Height="16"
                                                  MinWidth="16"
                                                  Margin="3,0,0,0"
                                                  VerticalAlignment="Center"
                                                  Syncfusion:VisualContainer.WantsMouseInput="True"
                                                  IsEnabled="{Binding RelativeSource={RelativeSource TemplatedParent},
                                                                      Path=IsCheckBoxEnabled,
                                                                      Mode=TwoWay,
                                                                      UpdateSourceTrigger=PropertyChanged}"
                                                  IsThreeState="True"
                                                  Visibility="{Binding Path=HasChildNodes,
                                                                       RelativeSource={RelativeSource TemplatedParent},
                                                                       Converter={StaticResource boolToVisibilityConverter},
                                                                       Mode=TwoWay}" />
                                        <Grid Grid.Column="2"
                                              Margin="3,0,0,0"
                                              Background="{TemplateBinding Background}">
                                            <ContentPresenter />
                                            <Border x:Name="PART_CurrentCellBorder"
                                                    Margin="0,0,0,0"
                                                    Background="Transparent"
                                                    BorderBrush="{TemplateBinding CurrentCellBorderBrush}"
                                                    BorderThickness="{TemplateBinding CurrentCellBorderThickness}"
                                                    IsHitTestVisible="False"
                                                    Visibility="Collapsed" />
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
                                    </Grid>
                                </Border>
                                <VisualStateManager.VisualStateGroups>
                                    <VisualStateGroup x:Name="IndicationStates">
                                        <VisualState x:Name="NoError" />
                                        <VisualState x:Name="HasError">
                                            <Storyboard>
                                                <ObjectAnimationUsingKeyFrames BeginTime="00:00:00"
                                                                               Storyboard.TargetName="PART_InValidCellBorder"
                                                                               Storyboard.TargetProperty="(UIElement.Visibility)">
                                                    <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}" />
                                                </ObjectAnimationUsingKeyFrames>
                                            </Storyboard>
                                        </VisualState>
                                    </VisualStateGroup>
                                    <VisualStateGroup x:Name="CurrentStates">
                                        <VisualState x:Name="Regular" />
                                        <VisualState x:Name="Current">
                                            <Storyboard>
                                                <ObjectAnimationUsingKeyFrames BeginTime="00:00:00"
                                                                               Storyboard.TargetName="PART_CurrentCellBorder"
                                                                               Storyboard.TargetProperty="(UIElement.Visibility)">
                                                    <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}" />
                                                </ObjectAnimationUsingKeyFrames>
                                            </Storyboard>
                                        </VisualState>
                                    </VisualStateGroup>
                                </VisualStateManager.VisualStateGroups>
                            </Grid>
                        </ControlTemplate>
                    </Setter.Value>
                </Setter>
            </Style>
        </ResourceDictionary>
</Window.Resources>
{% endhighlight %}
{% highlight c# %}
public class BoolToVisibilityConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {

        if ((bool)value)
            return Visibility.Visible;
        return Visibility.Collapsed;
    }

    public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {

        if ((Visibility)value == Visibility.Visible)
            return true;
        return false;
    }
}
{% endhighlight %}
{% endtabs %}

Here, node CheckBox is collapsed for leaf nodes.

![WPF SfTreeGrid Node-CheckBox Image4](Node-CheckBox_images/Node-CheckBox_img4.png)

## Handling Selection based on CheckBox State

SfTreeGrid has following modes for processing selection based on check box state.

1. Default – Selection and state of checkbox works independent of each other.
2. SelectOnCheck – Row can be selected or deselected based on state of checkbox.
3. SynchronizeSelection – Row can be selected or deselected based on state of checkbox and vice versa.

**Default mode**

If you don’t want to affect the selection while checking/unchecking the node CheckBox, you need to set [SfTreeGrid.CheckBoxSelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CheckBoxSelectionMode) as `Default`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       CheckBoxSelectionMode="Default"
                       ItemsSource="{Binding PersonDetails}"
                       ShowCheckBox="True"/>

{% endhighlight %}
{% endtabs %}
{% tabs %}
{% highlight c# %}
treeGrid.CheckBoxSelectionMode = CheckBoxSelectionMode.Default;
{% endhighlight %}
{% endtabs %}

![WPF SfTreeGrid Node-CheckBox Image5](Node-CheckBox_images/Node-CheckBox_img5.png)

**SelectOnCheck**

If you want to select/deselect the rows using node CheckBox only, you need to set [SfTreeGrid. CheckBoxSelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CheckBoxSelectionMode) as `SelectOnCheck`. 
Navigation, editing and programmatic selection are not supported in this mode.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       CheckBoxSelectionMode="SelectOnCheck"
                       ItemsSource="{Binding PersonDetails}"
                       ShowCheckBox="True"/>

{% endhighlight %}
{% highlight c# %}
treeGrid.CheckBoxSelectionMode = CheckBoxSelectionMode.SelectOnCheck;
{% endhighlight %}
{% endtabs %}

![WPF SfTreeGrid Node-CheckBox Image6](Node-CheckBox_images/Node-CheckBox_img6.png)

**SynchronizeSelection**

If you want to synchronize the selection with node CheckBox’s IsChecked state, you need to set [SfTreeGrid.CheckBoxSelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CheckBoxSelectionMode) as `SynchronizeSelection`. In this mode, you can select by checking checkbox and selecting/deselecting the row will check/uncheck the corresponding node checkbox.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       CheckBoxSelectionMode="SynchronizeSelection"
                       ItemsSource="{Binding PersonDetails}"
                       ShowCheckBox="True"/>

{% endhighlight %}
{% highlight c# %}
treeGrid.CheckBoxSelectionMode = CheckBoxSelectionMode.SynchronizeSelection;
{% endhighlight %}
{% endtabs %}

![WPF SfTreeGrid Node-CheckBox Image7](Node-CheckBox_images/Node-CheckBox_img7.png)

N>
* Recursive checking is not supported when selection mode is single.
* CheckBox selection is not supported if selection mode in None.

## Events

### NodeCheckStateChanged

[NodeCheckStateChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event triggered when user check or uncheck the node check box.

{% tabs %}
{% highlight c# %}
treeGrid.NodeCheckStateChanged += TreeGrid_NodeCheckStateChanged;

private void TreeGrid_NodeCheckStateChanged(object sender, NodeCheckStateChangedEventArgs e)
{
    var node = e.Node;
}
{% endhighlight %}
{% endtabs %}

## Programmatically Processing Node CheckBox

You can change the state of node checkbox programmatically by calling [SetCheckedState](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeNode.html#Syncfusion_UI_Xaml_TreeGrid_TreeNode_SetCheckedState_System_Nullable_System_Boolean__System_Boolean_System_Boolean_) method as below,

{% tabs %}
{% highlight c# %}
var treeNode = treeGrid.View.Nodes[0];
treeNode.SetCheckedState(true);
{% endhighlight %}
{% endtabs %}

If you want to restrict the `IsChecked` update of the parent and child nodes (when [SfTreeGrid.EnableRecursiveChecking](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_EnableRecursiveChecking) is `true`), you can pass default parameter values as `false` in [SetCheckedState](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeNode.html#Syncfusion_UI_Xaml_TreeGrid_TreeNode_SetCheckedState_System_Nullable_System_Boolean__System_Boolean_System_Boolean_) method.

{% tabs %}
{% highlight c# %}
var treeNode = treeGrid.View.Nodes[0];
treeNode.SetCheckedState(true, false, false);
{% endhighlight %}
{% endtabs %}

## Getting Checked nodes

You can get the checked nodes collection using [GetCheckedNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_GetCheckedNodes_System_Boolean_) method.

{% tabs %}
{% highlight c# %}
var nodes = treeGrid.GetCheckedNodes();
{% endhighlight %}
{% endtabs %}

If you want to get all the checked nodes even though they are not in view, you can pass parameter as ‘true’ in `GetCheckedNodes` method.

{% tabs %}
{% highlight c# %}
var nodes = treeGrid.GetCheckedNodes(true);
{% endhighlight %}
{% endtabs %}
