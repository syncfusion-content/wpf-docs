---
layout: post
title: Getting Started | SfRating | wpf | Syncfusion
description: getting started
platform: wpf
control: SfRating
documentation: ug
---

# Getting Started

 Namespace:  Syncfusion.Windows.Controls.Input
 Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll) 

The following code sample shows how to create the rating from code-behind and XAML:

{%tabs%}
{%highlight xml%}





<Page xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf">



    <Grid>

        <editors:SfRating/>           

    </Grid>

</Page>

{%endhighlight%}


{%highlight c#%}



SfRating rating = new SfRating();

{%endhighlight%}
{%endtabs%}

