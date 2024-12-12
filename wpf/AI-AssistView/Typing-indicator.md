---
layout: post
title: TypingIndicator in WPF AI AssistView control | Syncfusion
description: Learn about the typing indicator feature displayed in the AI AssistView control while the AI processes or generates a response.
platform: wpf
control: SfAIAssistView
documentation: ug
---

# Initialize the typing indicator in WPF AI AssistView

By using the [TypingIndicator](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Chat.SfAIAssistView.html#Syncfusion_UI_Xaml_Chat_SfAIAssistView_TypingIndicator) property, a typing indicator is shown while the AI is processing or generating a response, giving users real-time feedback and enhancing conversational flow

{% tabs %}

{% highlight xaml %}

<Page
    x:Class="GettingStarted.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:GettingStarted"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.Chat"
    mc:Ignorable="d"
    Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
    <Grid>
      <syncfusion:SfAIAssistView   CurrentUser="{Binding CurrentUser}"
                                   Suggestions="{Binding Suggestion}"
                                   ShowTypingIndicator="True"
                                   TypingIndicator="{Binding TypingIndicator}"
                                   Messages="{Binding Chats}"/>
    </Grid>
</Page>

{% endhighlight %} 

{% highlight C# %}

 public class ViewModel : INotifyPropertyChanged
 {
     private ObservableCollection<object> chats;
     private Author currentUser;
     private IEnumerable<string> suggestion;
     private TypingIndicator typingIndicator;

     public ViewModel()
     {
         this.Chats = new ObservableCollection<object>();          
         this.CurrentUser = new Author { Name="John"};
         Suggestion = new ObservableCollection<string>();
         TypingIndicator = new TypingIndicator { Author = new Author { Name = "AI" } };
         this.GenerateMessages();
     }

     private async void GenerateMessages()
     {
         this.Chats.Add( new TextMessage { Author = CurrentUser, Text = "What is WPF?" } );        
         await Task.Delay(1000);
         this.Chats.Add( new TextMessage { Author = new Author { Name = "Bot" }, Text = "WPF is a user interface layer that contains modern controls and styles for building Windows apps." });
         Suggestion = new ObservableCollection<string> {"What is the future of WPF?", "What is XAML?", "What is the difference between WPF 2 and WPF 3?" };
     }

    
     public IEnumerable<string> Suggestion
     {
        get
        {
         return this.suggestion;
        }
        set
        {
         this.suggestion = value;
         RaisePropertyChanged("Suggestion");
        }
     }

     public ObservableCollection<object> Chats
     {
         get
         {
             return this.chats;
         }
         set
         {
             this.chats = value;
             RaisePropertyChanged("Messages");
         }
     }

     public Author CurrentUser
     {
         get
         {
             return this.currentUser;
         }
         set
         {
             this.currentUser = value;
             RaisePropertyChanged("CurrentUser");
         }
     }

      
    public TypingIndicator TypingIndicator
    {
        get
        {
            return this.typingIndicator;
        }
        set
        {
            this.typingIndicator = value;
            RaisePropertyChanged("TypingIndicator");
        }
    }


     public void RaisePropertyChanged(string propName)
     {
         if (PropertyChanged != null)
         {
             PropertyChanged(this, new PropertyChangedEventArgs(propName));
         }
     }


     public event PropertyChangedEventHandler PropertyChanged;
  }

{% endhighlight %}
{% endtabs %}