---
layout: post
title: NonAccessibleBlocks| SfSchedule | Wpf | Syncfusion
description: nonaccessibleblocks 
platform: wpf
control: SfSchedule
documentation: ug
---

# NonAccessibleBlocks 

 For a particular Starting and Ending time the block could not be accessed by setting the NonAccessibleBlocks property.
{% tabs %}
 {% highlight html %}


              <Schedule:SfSchedule ScheduleType="Week"  IntervalHeight="30">

            <Schedule:SfSchedule.NonAccessibleBlocks>

                <Schedule:NonAccessibleBlock Background="LightPink" StartHour="6.00" EndHour="8.00" Label="Non Accessible Block">

                </Schedule:NonAccessibleBlock> 

            </Schedule:SfSchedule.NonAccessibleBlocks>

        </Schedule:SfSchedule>



{% endhighlight  %}
{% highlight c# %}



            SfSchedule schedule = new SfSchedule();

            schedule.ScheduleType = ScheduleType.Week;

            schedule.NonAccessibleBlocks.Add(new NonAccessibleBlock() { Background = new SolidColorBrush(Colors.LightPink), StartHour = 6.00, EndHour = 8.00, Label = "Non Accessible Block" });

            this.grid.Children.Add(schedule);  


{% endhighlight  %}
{% endtabs %}


![](NonAccessibleBlocks_images/NonAccessibleBlocks_img1.png)





## NonAccessibleBlockTemplate 

The  NonAccessibleBlockTemplate can be customized by NonAccessibleBlockTemplate property.

{% tabs %}
{% highlight html %}




    <Grid Background="White" Name="grid">

        <Schedule:SfSchedule  Name="schedule" ScheduleType="Week"  IntervalHeight="30">

            <Schedule:SfSchedule.NonAccessibleBlockTemplate>

                <DataTemplate>

                    <Border Height="50" Width="60" Background="LightGreen">

                        <TextBlock Text="Main Block"></TextBlock>

                            </Border>

                </DataTemplate>

            </Schedule:SfSchedule.NonAccessibleBlockTemplate>

        </Schedule:SfSchedule>

    </Grid>


{% endhighlight  %}
{% highlight c# %}



            SfSchedule schedule = new SfSchedule();

            schedule.NonAccessibleBlocks.Add(new NonAccessibleBlock() { StartHour = 2,EndHour = 4, Label = "Main Block" });

            schedule.NonAccessibleBlockTemplate = (DataTemplate)this.Resources["NonAccessibleBlockTemplate"];

            this.grid.Children.Add(schedule);



{% endhighlight  %}
{% endtabs %}

![](NonAccessibleBlocks_images/NonAccessibleBlocks_img2.png)





