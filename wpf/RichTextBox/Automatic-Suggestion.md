---
title: Automatic Suggestion of RichTextBox | WPF | Syncfusion
description: Automatic Suggestion
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: Automatic Suggestion
---
# Automatic Suggestion

## Automatic Suggestion functionality for using @mentions in SfRichTextBoxAdv control
SfRichTextBoxAdv control shows an inline dropdown with a list of suggested names while type the given mention character (ex: @ symbol). The list of names will filter as you type more letters. You can hit the Tab or Enter key on your keyboard to select the top option, use the arrow keys to highlight other options then hit Tab or Enter, or use your mouse to click any option in the list.
The selected item from the suggestion list will be inserted as hyperlink with the display text and its respective link.

The following sample code demonstrates how to enable spell checker in SfRichTextBoxAdv.
![Enable Spell Checker](Automatic-Suggestion_images/autosuggestion1.PNG)

{% tabs %}
{% highlight xaml %}
<Window.Resources>
        <x:Array Type="{x:Type RichTextBoxAdv:NameSuggestionItem}" x:Key="suggestionItems">
            <RichTextBoxAdv:NameSuggestionItem Name = "Nancy Davolio" Link="mailto:nancy.davolio@northwindtraders.com" ImageSource="/Assets/People_Circle0.png" />
            <RichTextBoxAdv:NameSuggestionItem Name = "Andrew Fuller" Link="mailto:andrew.fuller@northwindtraders.com" ImageSource="/Assets/People_Circle5.png"/>
            <RichTextBoxAdv:NameSuggestionItem Name = "Steven Buchanan" Link="mailto:steven.buchanan@northwindtraders.com" ImageSource="/Assets/People_Circle18.png"/>
        </x:Array>
</Window.Resources>
    <Grid>
        <RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextboxadv" LayoutType="Continuous">
            <RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
                <RichTextBoxAdv:SuggestionSettings>
                    <RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
                        <RichTextBoxAdv:NameSuggestionProvider     ItemsSource="{StaticResource suggestionItems}">
                        </RichTextBoxAdv:NameSuggestionProvider>
                    </RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
                </RichTextBoxAdv:SuggestionSettings>
            </RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
        </RichTextBoxAdv:SfRichTextBoxAdv>
    </Grid>
{% endhighlight %}

{% highlight C# %}
ISuggestionProvider suggestionProvider = new NameSuggestionProvider();
            List<NameSuggestionItem> suggestionItems = new List<NameSuggestionItem>();

            NameSuggestionItem suggestionItem = new NameSuggestionItem();
            suggestionItem.Name = "Nancy Davolio";
            suggestionItem.Link = "mailto:nancy.davolio@northwindtraders.com";
            BitmapImage bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"..\..\Assets\People_Circle0.png").FullName));
            suggestionItem.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem);

            suggestionItem = new NameSuggestionItem();
            suggestionItem.Name = "Andrew Fuller";
            suggestionItem.Link = "mailto:andrew.fuller@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"..\..\Assets\People_Circle5.png").FullName));
            suggestionItem.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem);

            suggestionItem = new NameSuggestionItem();
            suggestionItem.Name = "Steven Buchanan";
            suggestionItem.Link = "mailto:steven.buchanan@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"..\..\Assets\People_Circle18.png").FullName));
            suggestionItem.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem);

            (suggestionProvider as NameSuggestionProvider).ItemsSource = suggestionItems;
            richTextboxadv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider);
{% endhighlight %}

{% highlight VB %}
Dim suggestionProvider As ISuggestionProvider = New NameSuggestionProvider()
	Dim suggestionItems As List<NameSuggestionItem> = New List<NameSuggestionItem>()
	
	Dim suggestionItem As NameSuggestionItem = New NameSuggestionItem()
	suggestionItem.Name = "Nancy Davolio"
	suggestionItem.Link = "mailto:nancy.davolio@northwindtraders.com"
	Dim bitmapImage As BitmapImage = New BitmapImage(New Uri(New DirectoryInfo("..\..\Assets\People_Circle0.png").FullName))
	suggestionItem.ImageSource = bitmapImage
	suggestionItems.Add(suggestionItem)
	
	suggestionItem = New NameSuggestionItem()
	suggestionItem.Name = "Andrew Fuller"
	suggestionItem.Link = "mailto:andrew.fuller@northwindtraders.com"
	bitmapImage = New BitmapImage(New Uri(New DirectoryInfo("..\..\Assets\People_Circle5.png").FullName))
	suggestionItem.ImageSource = bitmapImage
	suggestionItems.Add(suggestionItem)
	
	suggestionItem = New NameSuggestionItem()
	suggestionItem.Name = "Steven Buchanan"
	suggestionItem.Link = "mailto:steven.buchanan@northwindtraders.com"
	bitmapImage = New BitmapImage(New Uri(New DirectoryInfo("..\..\Assets\People_Circle18.png").FullName))
	suggestionItem.ImageSource = bitmapImage
	suggestionItems.Add(suggestionItem)
	
	TryCast(suggestionProvider, NameSuggestionProvider).ItemsSource = suggestionItems
    richTextBoxAdv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider)
{% endhighlight %}
{% endtabs %}

## Customize the SuggestionBox ItemTemplate and Style
By default, the drop-down window lists the filtered items as an image, display text and link. If you want to remove the image or link. You can write your own item Template.

The following sample code demonstrates how to modify the suggestion box item template and style.
{% tabs %}
{% highlight xaml %}
<Window.Resources>
        <x:Array Type="{x:Type RichTextBoxAdv:NameSuggestionItem}" x:Key="suggestionItems">
            <RichTextBoxAdv:NameSuggestionItem Name = "Nancy Davolio" Link="mailto:nancy.davolio@northwindtraders.com"  />
            <RichTextBoxAdv:NameSuggestionItem Name = "Andrew Fuller" Link="mailto:andrew.fuller@northwindtraders.com" />
            <RichTextBoxAdv:NameSuggestionItem Name = "Steven Buchanan" Link="mailto:steven.buchanan@northwindtraders.com"/>
        </x:Array>
        <Style x:Key="SuggestionBoxStyle" TargetType="ListBox">
            <Setter Property="MinWidth" Value="300" />
            <Setter Property="MinHeight" Value="250" />
            <Setter Property="Background" Value="#FFDBF5FB"/>
            <Setter Property="ItemTemplate">
                <Setter.Value>
                    <DataTemplate DataType="local:NameSuggestionItem">
                        <StackPanel Orientation="Vertical" Height="50" VerticalAlignment="Center" Margin="12,15,0,0">
                            <TextBlock Text="{Binding Name}" FontFamily="microsoft sans serif" FontSize="14"  />
                            <TextBlock Text="{Binding Link}" FontFamily="microsoft sans serif" Foreground="Gray" FontSize="10" />
                        </StackPanel>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
</Window.Resources>
    <Grid>
        <RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextboxadv" LayoutType="Continuous">
            <RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
                <RichTextBoxAdv:SuggestionSettings>
                    <RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
                        <RichTextBoxAdv:NameSuggestionProvider ItemsSource="{StaticResource suggestionItems}" 
                                                               SuggestionBoxStyle="{StaticResource SuggestionBoxStyle}">
                        </RichTextBoxAdv:NameSuggestionProvider>
                    </RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
                </RichTextBoxAdv:SuggestionSettings>
            </RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
        </RichTextBoxAdv:SfRichTextBoxAdv>
    </Grid>
{% endhighlight %}
{% endtabs %}

![Modify Suggestion Box Item](Automatic-Suggestion_images/autosuggestion2.PNG)

## Custom mention character
By default, @ is a mention character. But any character can be used as mention character.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
        <x:Array Type="{x:Type RichTextBoxAdv:NameSuggestionItem}" x:Key="suggestionItems">
            <RichTextBoxAdv:NameSuggestionItem Name = "Nancy Davolio" Link="mailto:nancy.davolio@northwindtraders.com" ImageSource="/Assets/People_Circle0.png" />
            <RichTextBoxAdv:NameSuggestionItem Name = "Andrew Fuller" Link="mailto:andrew.fuller@northwindtraders.com" ImageSource="/Assets/People_Circle5.png"/>
            <RichTextBoxAdv:NameSuggestionItem Name = "Steven Buchanan" Link="mailto:steven.buchanan@northwindtraders.com" ImageSource="/Assets/People_Circle18.png"/>
        </x:Array>
</Window.Resources>
    <Grid>
        <RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextboxadv" LayoutType="Continuous">
            <RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
                <RichTextBoxAdv:SuggestionSettings>
                    <RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
                        <RichTextBoxAdv:NameSuggestionProvider MentionCharacter="#" 
                                                               ItemsSource="{StaticResource suggestionItems}">
                        </RichTextBoxAdv:NameSuggestionProvider>
                    </RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
                </RichTextBoxAdv:SuggestionSettings>
            </RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
        </RichTextBoxAdv:SfRichTextBoxAdv>
    </Grid>
{% endhighlight %}

{% highlight C# %}
ISuggestionProvider suggestionProvider = new NameSuggestionProvider();
            suggestionProvider.MentionCharacter = '#';
            List<NameSuggestionItem> suggestionItems = new List<NameSuggestionItem>();

            NameSuggestionItem suggestionItem1 = new NameSuggestionItem();
            suggestionItem1.Name = "Nancy Davolio";
            suggestionItem1.Link = "mailto:nancy.davolio@northwindtraders.com";
            BitmapImage bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"..\..\Assets\People_Circle0.png").FullName));
            suggestionItem1.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem1);

            NameSuggestionItem suggestionItem2 = new NameSuggestionItem();
            suggestionItem2.Name = "Andrew Fuller";
            suggestionItem2.Link = "mailto:andrew.fuller@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"..\..\Assets\People_Circle5.png").FullName));
            suggestionItem2.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem2);

            NameSuggestionItem suggestionItem3 = new NameSuggestionItem();
            suggestionItem3.Name = "Steven Buchanan";
            suggestionItem3.Link = "mailto:steven.buchanan@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"..\..\Assets\People_Circle18.png").FullName));
            suggestionItem3.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem3);

            (suggestionProvider as NameSuggestionProvider).ItemsSource = suggestionItems;
            richTextboxadv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider);
{% endhighlight %}
{% endtabs %}

![Mention Character](Automatic-Suggestion_images/autosuggestion3.PNG)

## Multiple mention character
You can use two or more mention characters at a time. And each character can have different item source and suggestion box style.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
        <Style x:Key="SuggestionBoxStyle" TargetType="ListBox">
            <Setter Property="MinWidth" Value="300" />
            <Setter Property="MinHeight" Value="250" />
            <Setter Property="ItemTemplate">
                <Setter.Value>
                    <DataTemplate DataType="local:NameSuggestionItem">
                        <StackPanel Orientation="Vertical" Height="50" Width="200" VerticalAlignment="Center" Margin="12,15,0,0">
                            <TextBlock Text="{Binding Name}" FontFamily="microsoft sans serif" FontSize="14"  />
                            <TextBlock Text="{Binding Link}" FontFamily="microsoft sans serif" Foreground="Gray" FontSize="10" />
                        </StackPanel>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
        
        <x:Array Type="{x:Type RichTextBoxAdv:NameSuggestionItem}" x:Key="suggestionItems">
            <RichTextBoxAdv:NameSuggestionItem Name = "Nancy Davolio" Link="mailto:nancy.davolio@northwindtraders.com" ImageSource="/Assets/People_Circle0.png" />
            <RichTextBoxAdv:NameSuggestionItem Name = "Andrew Fuller" Link="mailto:andrew.fuller@northwindtraders.com" ImageSource="/Assets/People_Circle5.png"/>
            <RichTextBoxAdv:NameSuggestionItem Name = "Steven Buchanan" Link="mailto:steven.buchanan@northwindtraders.com" ImageSource="/Assets/People_Circle18.png"/>
        </x:Array>

        <x:Array Type="{x:Type RichTextBoxAdv:NameSuggestionItem}" x:Key="suggestionItems01">
            <RichTextBoxAdv:NameSuggestionItem Name = "Desktop App" Link="10 queries"  />
            <RichTextBoxAdv:NameSuggestionItem Name = "Mobile App" Link="13 queries" />
            <RichTextBoxAdv:NameSuggestionItem Name = "Web App" Link="15 queries"/>
        </x:Array>
</Window.Resources>
    <Grid>
        <RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextboxadv" LayoutType="Continuous">
            <RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
                <RichTextBoxAdv:SuggestionSettings>
                    <RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
                        <RichTextBoxAdv:NameSuggestionProvider 
                                                               ItemsSource="{StaticResource suggestionItems}">
                        </RichTextBoxAdv:NameSuggestionProvider>
                        <RichTextBoxAdv:NameSuggestionProvider MentionCharacter="#" 
                                                               ItemsSource="{StaticResource suggestionItems01}"
                                                               SuggestionBoxStyle="{StaticResource SuggestionBoxStyle}">
                        </RichTextBoxAdv:NameSuggestionProvider>
                    </RichTextBoxAdv:SuggestionSettings.SuggestionProviders>
                </RichTextBoxAdv:SuggestionSettings>
            </RichTextBoxAdv:SfRichTextBoxAdv.SuggestionSettings>
        </RichTextBoxAdv:SfRichTextBoxAdv>
    </Grid>
{% endhighlight %}

{% highlight C# %}
ISuggestionProvider suggestionProvider = new NameSuggestionProvider();
            List<NameSuggestionItem> suggestionItems = new List<NameSuggestionItem>();

            NameSuggestionItem suggestionItem1 = new NameSuggestionItem();
            suggestionItem1.Name = "Nancy Davolio";
            suggestionItem1.Link = "mailto:nancy.davolio@northwindtraders.com";
            BitmapImage bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"..\..\Assets\People_Circle0.png").FullName));
            suggestionItem1.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem1);

            NameSuggestionItem suggestionItem2 = new NameSuggestionItem();
            suggestionItem2.Name = "Andrew Fuller";
            suggestionItem2.Link = "mailto:andrew.fuller@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"..\..\Assets\People_Circle5.png").FullName));
            suggestionItem2.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem2);

            NameSuggestionItem suggestionItem3 = new NameSuggestionItem();
            suggestionItem3.Name = "Steven Buchanan";
            suggestionItem3.Link = "mailto:steven.buchanan@northwindtraders.com";
            bitmapImage = new BitmapImage(new Uri(new DirectoryInfo(@"..\..\Assets\People_Circle18.png").FullName));
            suggestionItem3.ImageSource = bitmapImage;
            suggestionItems.Add(suggestionItem3);

            (suggestionProvider as NameSuggestionProvider).ItemsSource = suggestionItems;
            richTextboxadv.SuggestionSettings.SuggestionProviders.Add(suggestionProvider);

            ISuggestionProvider suggestionProviderAppType = new NameSuggestionProvider();
            suggestionProviderAppType.SuggestionBoxStyle = this.Resources["SuggestionBoxStyle"] as System.Windows.Style;
            suggestionProviderAppType.MentionCharacter = '#';
            List<NameSuggestionItem> appTypes = new List<NameSuggestionItem>();

            NameSuggestionItem desktopApp = new NameSuggestionItem();
            desktopApp.Name = "Desktop App";
            desktopApp.Link = "10 queries";
            desktopApp.ImageSource = bitmapImage;
            appTypes.Add(desktopApp);

            NameSuggestionItem mobileApp = new NameSuggestionItem();
            mobileApp.Name = "Mobile App";
            mobileApp.Link = "13 queries";
            mobileApp.ImageSource = bitmapImage;
            appTypes.Add(mobileApp);

            NameSuggestionItem webApp = new NameSuggestionItem();
            webApp.Name = "Web App";
            webApp.Link = "15 queries";
            webApp.ImageSource = bitmapImage;
            appTypes.Add(webApp);

            (suggestionProviderAppType as NameSuggestionProvider).ItemsSource = appTypes;
            richTextboxadv.SuggestionSettings.SuggestionProviders.Add(suggestionProviderAppType);
{% endhighlight %}
{% endtabs %}

## Display a message when suggestions are empty
When the entered item is not in the suggestion list, suggestionbox displays a text indicating that “We couldn’t find the person you were looking for.”. Th text to be displayed for this can be customized using the SuggestionBoxErrorMessage property in resource file.

![Multiple Mention Character](Automatic-Suggestion_images/autosuggestion4.PNG)

![suggestion empty](Automatic-Suggestion_images/autosuggestion5.PNG)

## Custom suggestion provider
By default, we have implemented and using ‘NameSuggestionProvider’ and ‘NameSuggestionItem’ as data type for suggestionbox. You can implement your own suggestion provider inheriting from ISuggestionProvider. Which helps you to customizing the Search and Insert functionalities.

{% tabs %}
{% highlight xaml %}

{% endhighlight %}

{% highlight C# %}

{% endhighlight %}
{% endtabs %}

## Custom Search
In default searching, it lists the items which contains the typed text. But you can modify it for example starts with or ends with.

{% tabs %}
{% highlight xaml %}

{% endhighlight %}

{% highlight C# %}

{% endhighlight %}
{% endtabs %}

![Custom Search]()
![Custom Search]()

## Custom insert selected item
By default, the selected item forms the suggestions list is inserted as hyperlink. But you can insert it as text or without hyperlink.

{% tabs %}
{% highlight xaml %}

{% endhighlight %}

{% highlight C# %}

{% endhighlight %}
{% endtabs %}

![Custom Insert]()
![Custom Insert]()

N> Supported from V18.4.0.30
    
[View Sample in GitHub]()
 


