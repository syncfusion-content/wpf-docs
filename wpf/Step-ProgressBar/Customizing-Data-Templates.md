---
layout: post
title: Customizing Data Templates| Step ProgressBar | Wpf | Syncfusion
description: customizing data templates
platform: wpf
control: Step ProgressBar
documentation: ug
---

# Customizing Data Templates

Data templates can be customized for items and content. The next sections explain how to customize data templates.

## Item Template

You can customize the content of StepViewItem by using ItemTemplate property. The following example shows how to use ItemTemplate, StepViewItem’s content is customized with DataTemplate. The value of item template is assigned to image path where it has been modified for a customized look and the content always same for entire stepview item.



{% highlight xaml %}

 <syncfusion:SfStepProgressBar
                x:Name="stepperControlName"
                Margin="40"
                ItemsSource="{Binding StepViewItems}"
                SelectedIndex="2">
                <syncfusion:SfStepProgressBar.ItemTemplate>
                    <DataTemplate>
                        <Grid>
                            <Path
                    Width="25"
                    Height="25"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M9 16.2L4.8 12l-1.4 1.4L9 19 21 7l-1.4-1.4L9 16.2z"
                    Fill="#2B579A"
                    Stroke="#2B579A" />
                        </Grid>
                    </DataTemplate>
                </syncfusion:SfStepProgressBar.ItemTemplate>
            </syncfusion:SfStepProgressBar>
{% endhighlight %}

Implementing the above code will create the following Step ProgressBar control.



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img1.png)



## Item Template Selector

Using ItemTemplateSelector, you can use different templates for items depending on specific constraints. The following example illustrates this.

1. Create the template selector in the code.


   ~~~csharp

	public class StepViewItemTemplateSelector : DataTemplateSelector
    {
        public override DataTemplate SelectTemplate(object item, DependencyObject container)
        {
            StepViewItem stepViewItem = item as StepViewItem;
            if (stepViewItem != null)
            {
                if (stepViewItem.Status == StepStatus.Indeterminate)
                {
                    return (item as StepViewItem).FindResource("IndeterminateContentTemplate") as DataTemplate;
                }
                else if (stepViewItem.Status == StepStatus.Active)
                {
                    return (item as StepViewItem).FindResource("ActiveContentTemplate") as DataTemplate;
                }
                else
                    return (item as StepViewItem).FindResource("InactiveContentTemplate") as DataTemplate;
            }
            return null;
        }
    }

   ~~~


2. Define the data templates in the Window’s resources.


   ~~~xaml


		<DataTemplate x:Key="ActiveContentTemplate">
            <Grid>
                <Path
                    Width="25"
                    Height="25"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M9 16.2L4.8 12l-1.4 1.4L9 19 21 7l-1.4-1.4L9 16.2z"
                    Fill="#2B579A"
                    Stroke="#2B579A" />
            </Grid>
        </DataTemplate>
        <DataTemplate x:Key="IndeterminateContentTemplate">
            <Grid>
                <Path
                    Width="25"
                    Height="25"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M12 4V1L8 5l4 4V6c3.31 0 6 2.69 6 6 0 1.01-.25 1.97-.7 2.8l1.46 1.46C19.54 15.03 20 13.57 20 12c0-4.42-3.58-8-8-8zm0 14c-3.31 0-6-2.69-6-6 0-1.01.25-1.97.7-2.8L5.24 7.74C4.46 8.97 4 10.43 4 12c0 4.42 3.58 8 8 8v3l4-4-4-4v3z"
                    Fill="#2B579A"
                    Stroke="#2B579A" />
            </Grid>
        </DataTemplate>
        <DataTemplate x:Key="InactiveContentTemplate">
            <Grid>
                <Path
                    Width="25"
                    Height="25"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"
                    Fill="#D2D2D2"
                    Stroke="#D2D2D2" />
            </Grid>
        </DataTemplate>
        
   ~~~



3. The template selector in the Window’s resources.




   ~~~xaml
		<local:StepViewItemTemplateSelector x:Key="stepViewItemTemplateSelector"

   ~~~



4. Use this template selector to choose a template for the Step ProgressBar control.


   ~~~xaml

	<syncfusion:SfStepProgressBar
                x:Name="stepperControlName"
                Margin="40"
                ItemsSource="{Binding StepViewItems}"
                SelectedIndex="2"
                ItemTemplateSelector="{StaticResource stepViewItemTemplateSelector}">
    </syncfusion:SfStepProgressBar>

   ~~~


This will generate the following Step ProgressBar control.



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img2.png)


## Marker Template Selector

With MarkerTemplateSelector, you can use different templates for StepViewItem appearance depending on specific constraints. The following example illustrates this.

1. Create the template selector in the code as follows.


   ~~~csharp

	public class StepViewItemMarkerTemplateSelector : DataTemplateSelector
    {
        public override DataTemplate SelectTemplate(object item, DependencyObject container)
        {
            StepViewItem stepViewItem = item as StepViewItem;
            if (stepViewItem != null)
            {
                if (stepViewItem.Status == StepStatus.Indeterminate)
                    return (item as StepViewItem).FindResource("InProgressDataTemplate") as DataTemplate;
                else if (stepViewItem.Status == StepStatus.Active)
                    return (item as StepViewItem).FindResource("CompletedDataTemplate") as DataTemplate;
                else
                    return (item as StepViewItem).FindResource("NotStartedDataTemplate") as DataTemplate;
            }
            return null;
        }
    }

   ~~~


2. Define the data templates in the Window’s resources.

   ~~~csharp

		 <DataTemplate x:Key="InProgressDataTemplate">
            <Grid>
                <Ellipse
                    Width="35"
                    Height="35"
                    Fill="#00ccb1"
                    Stroke="#00ccb1" />
                <Path
                    Width="12"
                    Height="12"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M8,0 C12.411011,0 16,3.5890198 16,8 16,12.411011 12.411011,16 8,16 3.5889893,16 0,12.411011 0,8 0,3.5890198 3.5889893,0 8,0 z"
                    Fill="White"
                    Stretch="Fill" />
            </Grid>
        </DataTemplate>
        <DataTemplate x:Key="CompletedDataTemplate">
            <Grid>
                <Ellipse
                    Width="35"
                    Height="35"
                    Fill="#00ccb1"
                    Stroke="#00ccb1" />
                <Path
                    Width="16"
                    Height="11"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Data="M15.288992,0 L15.997,0.70702839 5.7260096,11.000999 0,5.8859658 0.66601563,5.1399964 5.6870084,9.6239898 z"
                    Fill="White"
                    Stretch="Fill"
                    Stroke="White" />
            </Grid>
        </DataTemplate>
        <DataTemplate x:Key="NotStartedDataTemplate">
            <Grid>
                <Ellipse
                    Width="35"
                    Height="35"
                    Fill="#FFFFFF"
                    Stroke="#D2D2D2" />
            </Grid>
        </DataTemplate>

   ~~~


3. Create an instance of the template selector in the Window’s resources.

   ~~~csharp
   
	  <local:StepViewItemMarkerTemplateSelector x:Key="stepViewItemMarkerTemplateSelector" />

   ~~~



4. Now use MarkerTemplateSelector.

   ~~~csharp

		<syncfusion:SfStepProgressBar
                x:Name="stepperControlName"
                Margin="40"
                ItemsSource="{Binding StepViewItems}"
                MarkerTemplateSelector="{StaticResource stepViewItemMarkerTemplateSelector}"
                SelectedItemStatus="Indeterminate"
                ActiveConnectorColor="#00ccb1"
                SelectedIndex="2" >
                <syncfusion:SfStepProgressBar.ItemContainerStyle>
                    <Style TargetType="syncfusion:StepViewItem">
                        <Setter Property="Content" Value="{Binding ModelText}" />
                        <Setter Property="TextSpacing" Value="{Binding TitleSpace}" />
                        <Setter Property="MarkerWidth" Value="35"/>
                        <Setter Property="MarkerHeight" Value="35"/>
                    </Style>
                </syncfusion:SfStepProgressBar.ItemContainerStyle>

            </syncfusion:SfStepProgressBar>


   ~~~


This will populate the Step ProgressBar control.



![](Customizing-Data-Templates_images/Customizing-Data-Templates_img3.png)

  

