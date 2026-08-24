---
layout: post
title: Gestures in WPF Domain Updown control | Syncfusion®
description: Learn here all about Gestures support in Syncfusion® WPF Domain Updown (SfDomainUpDown) control and more.
platform: WPF
control: DomainUpDown
documentation: ug
---

# Gestures in WPF Domain Updown (SfDomainUpDown)

The `SfDomainUpDown` control supports the following input gestures for moving between items. All gestures are enabled by default.

## Mouse Wheel

The current item moves up or down when the mouse wheel is scrolled.

## Keyboard

* `Up Arrow` / `Down Arrow`: Move to the previous or next item.
* `Page Up` / `Page Down`: Move to the first or last item.
* `Home` / `End`: Jump to the first or last item.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDomainUpDown x:Name="domainUpDown" Width="200" ItemsSource="{Binding Employees}" />

{% endhighlight %}
{% endtabs %}

