---
layout: post
title: Cards | SfKanban | wpf | Syncfusion
description: This section describes about cards and it's customization. 
platform: wpf
control: SfKanban
documentation: ug
---

# Cards

The default elements of a card can be customized using the below properties of [`KanbanModel`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel.html).

* [`Title`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel~Title.html)         - Used to set the title of a card.
* [`ImageURL`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel~ImageURL.html)      - Used to set the image URL of a card. The image will be displayed at right side in default card template.
* [`Category`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel~Category.html)      - Used to set the category of a card. Based on the category the [`Cards`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanColumn~Cards.html) will be added to the respective columns. 
* [`Description`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel~Description.html)   - Used to set the description text of a card.
* [`ColorKey`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel~ColorKey.html)      - Used to specify the indicator [`ColorKey`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.IKanbanModel~ColorKey.html). The [`Color`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.ColorMapping~Color.html) value of the corresponding [`Key`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.ColorMapping~Key.html) should be added in [`IndicatorColorPalette`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.IndicatorColorPalette.html) collection of [`SfKanban`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban.html).
* [`Tags`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel~Tags.html)     - Used to specify the tags of a card. The tags will be displayed at bottom in default card template.
* [`ID`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel~ID.html)     - Used to set the ID of a card.

{% highlight C# %}

new KanbanModel()
{

    Title = "Universal App",

    ID = "27654",

    Description = "Incorporate feedback into functional specifications",

    Category = "Open",

    ColorKey = "Low",

    Tags = new string[] { "Deployment" },

    ImageURL = new Uri("/images/icon.jpg", UriKind.RelativeOrAbsolute )
};


{% endhighlight %}

Following code snippet is used to define the colors for each key.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban.IndicatorColorPalette>

    <kanban:ColorMapping Key="Low" Color="Blue"/>

    <kanban:ColorMapping Key="Normal" Color="Green" />

    <kanban:ColorMapping Key="High" Color="Red" />

</kanban:SfKanban.IndicatorColorPalette>

{% endhighlight %}

{% highlight C# %}

IndicatorColorPalette indicatorColorPalette = new IndicatorColorPalette();

indicatorColorPalette.Add(new ColorMapping() { Key = "Low", Color = Colors.Blue });

indicatorColorPalette.Add(new ColorMapping() { Key = "High", Color = Colors.Red });

indicatorColorPalette.Add(new ColorMapping() { Key = "Normal", Color = Colors.Green });

sfKanban.IndicatorColorPalette = indicatorColorPalette;

{% endhighlight %}

{% endtabs %}

![Customization of cards in WPF SfKanban](SfKanban_images/CardCustomization.png)

## Customizing kanban cards

The [`CardStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~CardStyle.html) property customizes the kanban cards. The following properties of [`CardStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~CardStyle.html) are used to customize its appearance:

* [`Background`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~Background.html) - Changes the background color of a card.
* [`BorderBrush`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~BorderBrush.html) - Changes the border brush of a card.
* [`BorderThickness`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~BorderThickness.html) - Changes the border thickness of a card.
* [`CornerRadius`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~CornerRadius.html) - Adds rounded corners to a card.
* [`IconVisibility`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~IconVisibility.html) - Changes the icon visibility of a card.
* [`IndicatorVisibility`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~IndicatorVisibility.html) - Changes the indicator visibility of a card.
* [`TagVisibility`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~TagVisibility.html) -  Changes the tag panel visibility of a card.
* [`TitleColor`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~TitleColor.html) - Changes the header color of a kanban card item.
* [`TitleFontSize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~TitleFontSize.html) - Changes the font size of a card title.
* [`TitleHorizontalAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~TitleHorizontalAlignment.html) - Changes the horizontal alignment of a card title.
* [`FontSize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~FontSize.html) - Changes the font size of a card description.
* [`Foreground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~Foreground.html) - Changes the foreground color of a card description.
* [`TagBackground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~TagBackground.html) - Changes the tag's background color.
* [`TagForeground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanCardStyle~TagForeground.html) - Changes the tag's foreground color.

## Template

You can replace the entire card template with your own design using [`SfKanban.CardTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~CardTemplate.html) property. The following code snippet and screenshot illustrates this.

{% highlight xaml %}

<kanban:SfKanban.CardTemplate>
    
    <DataTemplate>
    
        <Border BorderBrush="Black"
    
                BorderThickness="0.75"
    
                CornerRadius="10"
    
                Background="AliceBlue"
    
                Margin="0,5,0,5">
    
            <Grid Margin="10,5,5,10">
    
                <Grid.ColumnDefinitions>
    
                    <ColumnDefinition Width="7*" />
    
                    <ColumnDefinition Width="3*" />
                
                </Grid.ColumnDefinitions>
                
                <Grid.RowDefinitions>
                
                    <RowDefinition Height="Auto" />
                
                    <RowDefinition Height="Auto" />
                
                </Grid.RowDefinitions>
                
                <TextBlock Text="{Binding Path=Title}"
                
                           FontWeight="Bold"
                
                           FontSize="16" />
                
                <TextBlock Grid.Row="1"
                
                           FontSize="14"
                
                           HorizontalAlignment="Left"
                
                           Text="{Binding Description}"
                
                           TextWrapping="WrapWholeWords" />
                
                <Border Grid.Row="1"
                
                        Grid.Column="1"
                
                        Height="50"
                
                        CornerRadius="50"
                
                        Width="50"
                
                        BorderBrush="Silver"
                
                        BorderThickness=".75">
                
                    <Border.Background>
                
                        <ImageBrush ImageSource="{Binding ImageURL}" />
                
                    </Border.Background>
                
                </Border>
            
            </Grid>
        
        </Border>

    </DataTemplate>

</kanban:SfKanban.CardTemplate>

{% endhighlight %}


![Template support for cards in WPF SfKanban](SfKanban_images/CardTemplate.png)