---
layout: post
title: Populating Data in WPF Navigation Drawer Control | Syncfusion®
description: Learn about data population support in the Syncfusion® WPF Navigation Drawer (SfNavigationDrawer) control.
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Populating Data in WPF Navigation Drawer (SfNavigationDrawer)

This section explains how to populate data in the drawer menu.

## Populating Using Built-in Items

The WPF Navigation Drawer sidebar offers built-in item support of the type [NavigationItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.NavigationItem.html), which can be populated using the `Items` property.

The following properties are available in the `NavigationItem` and can be used to define each item in the navigation menu:

- **Header**: Represents the content of the `NavigationItem`.
- **Icon**: Represents the icon in the `NavigationItem`.
- **IconTemplate**: Used to display a custom icon in the `NavigationItem`. See the [IconTemplate](https://help.syncfusion.com/wpf/navigation-drawer/populating-data#icontemplate) section for more details.
- **IconMemberPath**: Used to display the icon for sub-items when providing the `ItemsSource`.
- **DisplayMemberPath**: Used to display the content for sub-items when providing the `ItemsSource`. See the [Hierarchical Data Binding](https://help.syncfusion.com/wpf/navigation-drawer/populating-data#hierarchical-data-binding) section for more details.
- **ExpanderTemplate**: Used to provide a custom view for the expander icon in both collapsed and expanded states.
- **Command**: Executes when the item is clicked. See the [Commands](https://help.syncfusion.com/wpf/navigation-drawer/commands-and-events) section for more details.
- **CommandParameter**: [CommandParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.NavigationItem.html#Syncfusion_UI_Xaml_NavigationDrawer_NavigationItem_CommandParameter) is a user-defined data value that can be passed to the `Command` when it is executed.
- **IsChildSelected**: Determines whether any sub-item is selected.
- **ItemType**: Defines the type of navigation item. See the [Different Item Types](https://help.syncfusion.com/wpf/navigation-drawer/populating-data#different-item-types) section for more details.
- **IsExpanded**: Determines whether the item is expanded or collapsed.
- **IsSelected**: Determines whether the item is selected.
- **SelectionBackground**: Used to customize the selection indicator in `NavigationItem`.
- **Items**: Used to populate the sub-items.



{% tabs %}
{% highlight xaml %}

    <syncfusion:SfNavigationDrawer
        x:Name="navigationDrawer"
        DisplayMode="Expanded">
        <syncfusion:NavigationItem
                Header="Inbox"
                IsExpanded="True"
                IsSelected="True">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M32.032381, 16.445429 L25.410999, ... />
            </syncfusion:NavigationItem.Icon>
            <syncfusion:NavigationItem Header="Primary">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M9.5189972,7.3780194C8.3389893,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Social">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M22.133972,14.194015C17.582977,... />
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Promotions">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M9.4614787,7.2521966C8.897512,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M42.128046,6.7269681 L18.53705,..../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Important">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M25.085007,5.9780004 L20.577011,...../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M6.9999996,48.353 L19,48.353 19,..../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem ItemType="Separator" />
        <syncfusion:NavigationItem Header="All Labels" ItemType="Header" />
        <syncfusion:NavigationItem Header="Starred">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M25.085007,5.9780004 L20.577011,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="All mail">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M12,32.999999 L26,32.999999 26,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Trash">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M17,12 L19,12 19,42 17,42z M10.998,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Spam">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M33.671003,29.293001 L39.214003,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Expanded;
            NavigationItemsCollection navigationSubItems = new NavigationItemsCollection();
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Primary",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M9.5189972,7.3780194C8.3389893,...),
                    ......
                },

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Social",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M22.133972,14.194015C17.582977,....),
                    .....
                },

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Promotions",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M9.4614787,7.2521966C8.897512,....),
                    .....
                },

            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Inbox",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M32.032381, 16.445429 L25.410999, ....),
                    ......
                },
                Items = navigationSubItems,
                IsExpanded = true,
                IsSelected=true
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Sent mail",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M42.128046,6.7269681 L18.53705,....),
                    ......
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Drafts",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M6.9999996,48.353 L19,....),
                    ....
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                ItemType = ItemType.Separator
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                ItemType = ItemType.Header,
                Header= "All Labels"
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Starred",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M25.085007,5.9780004 L20.577011,....),
                    .....
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "All mail",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M12,32.999999 L26,32.999999 26,....),
                    ......
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Trash",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M17,12 L19,12 19,42 17,42z M10.998,....),
                    ......
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Spam",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M33.671003,29.293001 L39.214003,....),
                    .........
                }
            });
            Label label = new Label();
            label.Content = "Content View";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            label.Height = 30;
            label.Width = 150;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}

![Populating with Data in WPF NavigationDrawer](populating_data_images/wpf-navigation-drawer-item.png)

> **Note:** View the [sample on GitHub](https://github.com/SyncfusionExamples/wpf-sfnavigationdrawer-samples/tree/main/Populating_With_Items).

### IconTemplate

The `IconTemplate` is used to provide a custom icon for the `NavigationItem`.

### Model

{% tabs %}
{% highlight c# %}

    public class Category
    {
        private string name;
        public string Name
        {
            get { return name; }
            set { name = value; }
        }

        private object icon;
        public object Icon
        {
            get { return icon; }
            set { icon = value; }
        }
    }

{% endhighlight %}
{% endtabs %}

### ViewModel

{% tabs %}
{% highlight c# %}

    public class ViewModel
    {
        public ObservableCollection<Category> Categories { get; set; }
        public ViewModel()
        {
            Categories = new ObservableCollection<Category>();
            Categories.Add(new Category()
            {
                Name = "Inbox",
                Icon = "Inbox.png"
            });
            Categories.Add(new Category()
            {
                Name = "Sent",
                Icon = "Sent.png"
            });
            Categories.Add(new Category()
            {
                Name = "Draft",
                Icon = "Draft.png"
            });
            Categories.Add(new Category()
            {
                Name = "Spam",
                Icon = "Spam.png"
            });
        }
    }

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

    <Window.DataContext>
        <local:ViewModel />
    </Window.DataContext>
    <Window.Resources>
        <Style x:Key="ItemStyle" TargetType="syncfusion:NavigationItem">
            <Setter Property="IconTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Image
                            Width="16"
                            Height="16"
                            Source="{Binding}" />
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </Window.Resources>
    <syncfusion:SfNavigationDrawer
        x:Name="navigationDrawer"
        DisplayMemberPath="Name"
        DisplayMode="Compact"
        IconMemberPath="Icon"
        ItemContainerStyle="{StaticResource ItemStyle}"
        ItemsSource="{Binding Categories}">
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="ContentView" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

            ViewModel viewModel = new ViewModel();
            DataContext = viewModel;

            Style navigationItemStyle = new Style(typeof(NavigationItem));
            FrameworkElementFactory image = new FrameworkElementFactory(typeof(Image));
            image.SetValue(Image.WidthProperty, (double)16);
            image.SetValue(Image.HeightProperty, (double)16);
            image.SetValue(Image.SourceProperty, new Binding());
            DataTemplate dataTemplate = new DataTemplate { VisualTree = image };
            navigationItemStyle.Setters.Add(new Setter(NavigationItem.IconTemplateProperty, dataTemplate));

            SfNavigationDrawer navigationDrawer =new SfNavigationDrawer();
            navigationDrawer.DisplayMemberPath = "Name";
            navigationDrawer.DisplayMode = DisplayMode.Compact;
            navigationDrawer.IconMemberPath = "Icon";
            navigationDrawer.ItemContainerStyle = navigationItemStyle;
            navigationDrawer.ItemsSource = viewModel.Categories;
            Label label = new Label();
            label.Content = "ContentView";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}

![WPF NavigationDrawer with Custom Icon](populating_data_images/wpf-navigation-drawer-custom-icon.png)

### Different Item Types

The WPF Navigation Drawer includes four built-in item types that can be set for each `NavigationItem`:

- **Tab**: Interactable and supports selection. Supports multi-level population with expand and collapse icons.
- **Button**: Behaves similarly to button controls. Supports interactions but does not have selection. It supports multi-level populations with expand and collapse icons.
- **Header**: Functions as a header label. Not selectable and only visible when the drawer menu is expanded.
- **Separator**: Acts as a separator line. Cannot have sub-items or interactions.
See also the [Populating Using Built-in Items](https://help.syncfusion.com/wpf/navigation-drawer/populating-data#populating-using-built-in-items) section.

> **Note:** The default ItemType value is Tab.

## Data Binding

The drawer menu can be populated via the [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_ItemsSource) property. It supports collections of objects bound through `ItemsSource`.

The [ItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_ItemTemplate) property customizes the item content when using `ItemsSource`, and the [IconMemberPath](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_IconMemberPath) property displays the icon of each item.

See the [Hierarchical Data Binding](https://help.syncfusion.com/wpf/navigation-drawer/populating-data#hierarchical-data-binding) section for more details.

### Model

{% tabs %}
{% highlight c# %}

    public class Model
    {
        private string item;
        public string Item
        {
            get { return item; }
            set { item = value; }
        }

        private object icon;
        public object Icon
        {
            get { return icon; }
            set { icon = value; }
        }
    }

{% endhighlight %}
{% endtabs %}

### ViewModel

{% tabs %}
{% highlight c# %}

    public class ViewModel
    {
        public ObservableCollection<Model> Items { get; set; }
        public ViewModel()
        {
            Items = new ObservableCollection<Model>();
            Items.Add(new Model()
            {
                Item = "Explore",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M6.0033803,5.705333 L7.0853577,....),
                    ..........
                }
            });
            Items.Add(new Model()
            {
                Item = "My music",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M2.5,10.701 C1.6729736,10.701 1,....),
                    ..........
                }
            });
            Items.Add(new Model()
            {
                Item = "Recommended",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M11.5,10 C11.224,10 11,....),
                    .........
                }
            });
            Items.Add(new Model()
            {
                Item = "Recent Playlist",
                Icon = new Path()
                {    
                    Data = Geometry.Parse("M6.9990103,3.0000041 L7.9990076,....),
                    ........
                }
            });
            Items.Add(new Model()
            {
                Item = "Radio",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M2.5,11.472009 L6.5,11.472009 C6.776,....),
                    ........
                }
            });
        }
    }

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

    <Window.DataContext>
        <local:ViewModel/>
    </Window.DataContext>
    <syncfusion:SfNavigationDrawer
            x:Name="navigationDrawer"
            DisplayMode="Compact"
            IconMemberPath="Icon"
            ItemsSource="{Binding Items}">
        <syncfusion:SfNavigationDrawer.ItemTemplate>
            <DataTemplate>
                <Label Content="{Binding Item}"/>
            </DataTemplate>
        </syncfusion:SfNavigationDrawer.ItemTemplate>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

            ViewModel viewModel = new ViewModel();
            this.DataContext = viewModel;
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Compact;
            navigationDrawer.IconMemberPath = "Icon";
            FrameworkElementFactory textBlock = new FrameworkElementFactory(typeof(TextBlock));
            textBlock.SetBinding(TextBlock.TextProperty, new Binding("Item"));
            DataTemplate template = new DataTemplate { VisualTree = textBlock };
            navigationDrawer.ItemTemplate = template;
            navigationDrawer.ItemsSource = viewModel.Items;
            Label label = new Label();
            label.Content = "Content View";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            label.Height = 30;
            label.Width = 150;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}

![Populating with Data in WPF NavigationDrawer](populating_data_images/wpf-navigation-drawer-data-binding.png)


## Hierarchical Data Binding

The control populates items using the [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_ItemsSource), also it allows the sub items.

When using the `ItemsSource` to show the content of the item achieved by [DisplayMemberPath](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_DisplayMemberPath) property and [ItemsContainerStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_ItemContainerStyle) property used to customize the items and allows to set the `ItemsSource` and `DisplayMemberPath` properties of the sub items.
                                    
### Model

{% tabs %}
{% highlight c# %}

    public class Model
    {
        public ObservableCollection<Model> SubItems { get; set; }

        private string item;
        public string Item
        {
            get { return item; }
            set { item = value; }
        }

        private object icon;
        public object Icon
        {
            get { return icon; }
            set { icon = value; }
        }
    }

{% endhighlight %}
{% endtabs %}

### ViewModel

{% tabs %}
{% highlight c# %}

     public class ViewModel
    {
        public ObservableCollection<Model> Items { get; set; }
        ObservableCollection<Model> SubItems = new ObservableCollection<Model>();
      
        public ViewModel()
        {
            Items = new ObservableCollection<Model>();
            SubItems.Add(new Model()
            {
                Item = "Item1",
            });
            SubItems.Add(new Model()
            {
                Item = "Item2",
            }); SubItems.Add(new Model()
            {
                Item = "Item3",
            });
            Items.Add(new Model()
            {
                Item = "Explore",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M6.0033803,5.705333 L7.0853577,...),
                    ............
                },
                SubItems=SubItems
            });
            Items.Add(new Model()
            {
                Item = "My music",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M2.5,10.701 C1.6729736,10.701 1,....),
                    .........
                }
            });
            Items.Add(new Model()
            {
                Item = "Recommended",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M11.5,10 C11.224,10 11,10.225 11,....),
                    ..........
                }
            });
            Items.Add(new Model()
            {
                Item = "Recent Playlist",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M6.9990103,3.0000041 L7.9990076,....),
                    .........
                }
            });
            Items.Add(new Model()
            {
                Item = "Radio",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M2.5,11.472009 L6.5,11.472009 C6.776,....),
                    ........
                }
            });
        }
    }

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

    <Window.DataContext>
        <local:ViewModel />
    </Window.DataContext>
    <Window.Resources>
        <Style x:Key="ItemStyle" TargetType="syncfusion:NavigationItem">
            <Setter Property="Icon" Value="{Binding Icon}" />
            <Setter Property="DisplayMemberPath" Value="Item" />
            <Setter Property="ItemsSource" Value="{Binding SubItems}" />
        </Style>
    </Window.Resources>
    <syncfusion:SfNavigationDrawer
        x:Name="navigationDrawer"
        DisplayMemberPath="Item"
        DisplayMode="Expanded"
        ItemContainerStyle="{StaticResource ItemStyle}"
        ItemsSource="{Binding Items}">
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% endtabs %}

![Hierarchical Data Binding in WPF NavigationDrawer](populating_data_images/wpf-navigation-drawer-hierarchical-data-binding.png)

N> View [sample](https://github.com/SyncfusionExamples/wpf-sfnavigationdrawer-samples/tree/main/Hierarchical_Data_Binding) in GitHub


## IndentationWidth

This property used to change the horizontal position of sub items. Left margin of the sub items depends on the [IndentationWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_IndentationWidth) property.

{% tabs %}
{% highlight xaml %}

   <syncfusion:SfNavigationDrawer
        x:Name="navigationDrawer"
        DisplayMode="Compact"
        IndentationWidth="40">
        <syncfusion:NavigationItem Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M32.032381, 16.445429 L25.410999, ..... />
            </syncfusion:NavigationItem.Icon>
            <syncfusion:NavigationItem Header="Primary">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M9.5189972,7.3780194C8.3389893,..../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Social">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M22.133972,14.194015C17.582977,..../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Promotions">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M9.4614787,7.2521966C8.897512,..../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M42.128046,6.7269681 L18.53705,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M6.9999996,48.353 L19,48.353 19,...../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% highlight c# %}

            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            navigationDrawer.DisplayMode = DisplayMode.Compact;
            navigationDrawer.IndentationWidth = 40;
            NavigationItemsCollection navigationSubItems = new NavigationItemsCollection();
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Primary",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M9.5189972,7.3780194C8.3389893,....),
                    ............
                },

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Social",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M22.133972,14.194015C17.582977,....),
                    .......
                }, 

            });
            navigationSubItems.Add(new NavigationItem()
            {
                Header = "Promotions",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M9.4614787,7.2521966C8.897512,....),
                    .....
                },

            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Inbox",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M32.032381, 16.445429 L25.410999,....),
                    ............
                },
                Items = navigationSubItems
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Sent mail",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M42.128046,6.7269681 L18.53705,....),
                    ..........
                }
            });
            navigationDrawer.Items.Add(new NavigationItem()
            {
                Header = "Drafts",
                Icon = new Path()
                {
                    Data = Geometry.Parse("M6.9999996,48.353 L19,48.353 19,....),
                    ........
                }
            });
            Label label = new Label();
            label.Content = "Content View";
            label.HorizontalAlignment = HorizontalAlignment.Center;
            label.VerticalAlignment = VerticalAlignment.Center;
            label.Height = 30;
            label.Width = 150;
            navigationDrawer.ContentView = label;
            this.Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}

See also [Populating using built in items](https://help.syncfusion.com/wpf/navigation-drawer/populating-data#populating-using-built-in-items) section.

![Changing Horizontal Position of WPF NavigationDrawer Items](populating_data_images/wpf-navigation-drawer-position.png)

## Popup support

The sub-items will be displayed in the popup when the drawer menu is collapsed in the compact and expanded display modes.

![WPF NavigationDrawer with Popup Menu](populating_data_images/wpf-navigation-drawer-popup-menu.png)
