---
layout: post
title: Cell Templates
description: Cell Templates
platform: wpf
control: PivotGrid
documentation: ug
---


## Cell Templates


The Cell Templates feature of PivotGrid allows you to define Templates and change the appearance of elements, such as column, row, summary, and value cells that are present in the Grid. The style for each element in the Grid should be defined of type PivotGridTemplateCell. The customized template can be defined for the following properties of PivotGrid:

* ColumnHeaderCellStyle
* RowHeaderCellStyle
* SummaryHeaderStyle
* SummaryCellStyle
* ValueCellStyle

The Expander’s in the Grid can also be customized with any UIElement and it should be named as “PART_Expander” to perform drill-up and drill-down operations.

#### Use Case Scenarios

Cell Templates will be useful when users require a rich User Interface (UI) appearance.

![C:/Users/dwarageshmb/Desktop/Vol 4 Docs/Images/PivotGrid Cell Template.png](Features_images/Features_img12.png)



#### Adding Cell Template

RowHeaderStyle of PivotGrid can be customized by using the Template, as shown in the following XAML. 

{% highlight xml %} 

[XAML]

<Style x:Key="rowStyle" TargetType="{x:Type syncfusion:PivotGridTemplateCell}">

 <Setter Property="Template">

  <Setter.Value>

    <ControlTemplate TargetType="{x:Type syncfusion:PivotGridTemplateCell}">

     <StackPanel Grid.Column="1" Orientation="Horizontal" Background="{StaticResource RowHeaderBackgroundBrush}">

       <!—Adding an Expander. -->                                

       <Expander Margin="1" x:Name="PART_Expander" IsExpanded="{Binding IsExpanded,RelativeSource={RelativeSource TemplatedParent}}" Visibility="{Binding Converter={StaticResource expanderVisiblityConverter}}" Grid.Column="0"/>

       <!—Adding an Image. -->

       <Image Margin="2,5,1,0" Grid.Column="1" VerticalAlignment="Top" HorizontalAlignment="Center">

         <Image.Style>

          <Style TargetType="{x:Type Image}">

           <Style.Triggers>

             <DataTrigger Binding="{Binding Path=Text, RelativeSource={RelativeSource TemplatedParent}}" Value="Car">

               <Setter Property="Source" Value="{StaticResource Car}"/>

               <Setter Property="Width" Value="32"/>

               <Setter Property="Height" Value="32"/>

             </DataTrigger>

             <DataTrigger Binding="{Binding Path=Text, RelativeSource={RelativeSource TemplatedParent}}" Value="Bike">

               <Setter Property="Source" Value="{StaticResource Bike}"/>

               <Setter Property="Width" Value="32"/>

               <Setter Property="Height" Value="32"/>

              </DataTrigger>                                              

             </Style.Triggers>                                                

            </Style>

           </Image.Style>

          </Image>

          <!-- A Textblock representing the Cell Value. -->

          <TextBlock Grid.Column="1" VerticalAlignment="Top" Margin="2,5,2,0"

            Text="{Binding Path=Text, RelativeSource={RelativeSource TemplatedParent}}" 

            TextWrapping="Wrap" FontFamily="Calibri" FontSize="12" />                                   

      </StackPanel>                            

     </ControlTemplate>

   </Setter.Value>

 </Setter>

</Style>



<syncfusion:PivotGridControl>

 <!—Specifying RowHeaderCellStyle. -->

 <syncfusion:PivotGridControl.RowHeaderCellStyle>

   <syncfusion:PivotGridCellStyle Style="{StaticResource rowStyle}"/>

  </syncfusion:PivotGridControl.RowHeaderCellStyle>

</syncfusion:PivotGridControl>

{% endhighlight %} 



![C:/Users/dwarageshmb/Desktop/Vol 4 Docs/Images/PivotGrid Cell Template.png](Features_images/Features_img13.png)



#### Sample Link

A sample application that illustrates Cell Template is distributed along with the Essential PivotGrid WPF installation and can be found at:

..\Syncfusion\BI\WPF\PivotAnalysis.WPF\Samples\Appearance\Cell Template Demo

#### To access a Cell Template sample

1. Open the Syncfusion Dashboard. 
2. Click Business Intelligence.
3. Click the WPF drop-down list, and then select Explore Samples. 
4. Navigate to PivotAnalysis.WPF > Samples > Appearance > Cell Template Demo.


