---
layout: post
title: Sequence Diagram Model in WPF Diagram control | Syncfusion®
description: Learn here all about Sequence Diagram Model support in Syncfusion® WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Sequence Diagram Model in WPF Diagram (SfDiagram)

A sequence diagram is an interaction diagram that demonstrates how objects interact with each other and the order of these interactions. The SfDiagram control provides comprehensive support for creating and visualizing UML sequence diagrams through the `UMLSequenceDiagramModel` class.

## Sequence Diagram Elements

A sequence diagram consists of several key elements: participants, messages, activation boxes, and fragments. Let's explore each of these in detail.

### Participants

Participants in a sequence diagram represent the entities that interact with each other, appearing at the top of the diagram with lifelines extending vertically downward.

#### Creating Participants

To create participants in your sequence diagram:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDiagram x:Name="Diagram">
    <syncfusion:SfDiagram.Model>
        <syncfusion:UMLSequenceDiagramModel>
            <syncfusion:UMLSequenceDiagramModel.Participants>
                <syncfusion:ParticipantCollection>
                    <!-- A human-shaped participant-->
                    <syncfusion:UMLSequenceParticipant ID="User" 
                                    Content="User" 
                                    IsActor="true" />

                    <!-- A rectangle-shaped participant -->
                    <syncfusion:UMLSequenceParticipant ID="System" 
                                    Content="System" 
                                    IsActor="false" ShowDestroyAtEnd="True" />
                </syncfusion:ParticipantCollection>
            </syncfusion:UMLSequenceDiagramModel.Participants>
        </syncfusion:UMLSequenceDiagramModel>
    </syncfusion:SfDiagram.Model>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}
// Create participants
ParticipantCollection participants = new ParticipantCollection
{
    // A human-shaped participant
    new UMLSequenceParticipant
    {
        ID = "User",            // Unique identifier for the participant
        Content = "User",       // Display text
        IsActor = true          // Set to true for actor, false for lifeline
    },
    
    // A rectangle-shaped participant
    new UMLSequenceParticipant
    {
        ID = "System",
        Content = "System",
        IsActor = false,
        ShowDestroyAtEnd = true  // Optional: Show destruction marker at end
    }
};

// Initialize Diagram
SfDiagram Diagram = new SfDiagram();

// Add participants to the model
Diagram.Model = new UMLSequenceDiagramModel()
{
    Participants = participants
};
{% endhighlight %}
{% endtabs %}

![ParticipantsExample](UML_SequenceDiagram_Images\ParticipantsExample.png)

#### Participant Properties

| Property | Type | Description |
|---|---|---|
| ID | object | A unique identifier for the participant |
| Content | string | The display text for the participant |
| IsActor | bool | Determines if the participant is displayed as an actor (true) or object (false) |
| ShowDestroyAtEnd | bool | Determines if a destruction marker (X) is shown at the end of the lifeline |
| ActivationBoxes | IEnumerable\<UMLSequenceActivationBox\> | Collection of activation boxes for this participant |

### Messages

Messages represent communication between participants and are displayed as arrows connecting lifelines.

#### Types of Messages

The `UMLSequenceMessageType` enum defines the following message types:

| Message Type | Description | Example |
|---|---|---|
| Synchronous | The sender waits for a response | ![Synchronous Message](UML_SequenceDiagram_Images\Synchronous.png) |
| Asynchronous | The sender continues without waiting | ![Asynchronous Message](UML_SequenceDiagram_Images\Asynchronous.png) |
| Reply | A response to a previous message | ![Reply Message](UML_SequenceDiagram_Images\Reply.png) |
| Create | Creates a new participant | ![Create Message](UML_SequenceDiagram_Images\Create.png) |
| Delete | Terminates a participant | ![Delete Message](UML_SequenceDiagram_Images\Delete.png)) |
| Self | A message from a participant to itself | ![Self Message](UML_SequenceDiagram_Images\Self.png) | |

#### Creating Messages

To create messages in your sequence diagram:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDiagram x:Name="Diagram">
    <syncfusion:SfDiagram.Model>
        <syncfusion:UMLSequenceDiagramModel>
            <syncfusion:UMLSequenceDiagramModel.Participants>
                <syncfusion:ParticipantCollection>
                    <!-- A human-shaped participant-->
                    <syncfusion:UMLSequenceParticipant ID="User" 
                                        Content="User" 
                                        IsActor="true" />

                    <!-- A rectangle-shaped participant -->
                    <syncfusion:UMLSequenceParticipant ID="System" 
                                        Content="System" 
                                        IsActor="false" ShowDestroyAtEnd="True" />

                    <syncfusion:UMLSequenceParticipant ID="Logger" 
                                        Content="Logger" 
                                        IsActor="false" ShowDestroyAtEnd="True" />

                    <syncfusion:UMLSequenceParticipant ID="SessionManager" 
                                        Content="SessionManager" 
                                        IsActor="false" />
                </syncfusion:ParticipantCollection>
            </syncfusion:UMLSequenceDiagramModel.Participants>

            <syncfusion:UMLSequenceDiagramModel.Messages>
                <syncfusion:MessageCollection>
                    <!-- Synchronous message -->
                    <syncfusion:UMLSequenceMessage ID="MSG1" 
                                    Content="Login Request" 
                                    FromParticipantID="User" 
                                    ToParticipantID="System" 
                                    Type="Synchronous" />

                    <!-- Reply message -->
                    <syncfusion:UMLSequenceMessage ID="MSG2" 
                                    Content="Login Response" 
                                    FromParticipantID="System" 
                                    ToParticipantID="User" 
                                    Type="Reply" />

                    <!-- Asynchronous message -->
                    <syncfusion:UMLSequenceMessage ID="MSG3" 
                                    Content="Log Event" 
                                    FromParticipantID="System" 
                                    ToParticipantID="Logger" 
                                    Type="Asynchronous" />

                    <!-- Create message -->
                    <syncfusion:UMLSequenceMessage ID="MSG4" 
                                    Content="Create Session" 
                                    FromParticipantID="System" 
                                    ToParticipantID="SessionManager" 
                                    Type="Create" />

                    <!-- Delete message -->
                    <syncfusion:UMLSequenceMessage ID="MSG5" 
                                    Content="Delete Session" 
                                    FromParticipantID="System" 
                                    ToParticipantID="SessionManager" 
                                    Type="Delete" />

                    <!-- Self message -->
                    <syncfusion:UMLSequenceMessage ID="MSG6" 
                                    Content="Validate Inputs" 
                                    FromParticipantID="System" 
                                    ToParticipantID="System" 
                                    Type="Self" />
                </syncfusion:MessageCollection>
            </syncfusion:UMLSequenceDiagramModel.Messages>
        </syncfusion:UMLSequenceDiagramModel>
    </syncfusion:SfDiagram.Model>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}
// Create Participants
var participants = new ParticipantCollection
{
    new UMLSequenceParticipant
    {
        ID = "User",
        Content = "User",
        IsActor = true
    },
    new UMLSequenceParticipant
    {
        ID = "System",
        Content = "System",
        IsActor = false,
        ShowDestroyAtEnd = true
    },
    new UMLSequenceParticipant
    {
        ID = "Logger",
        Content = "Logger",
        IsActor = false,
        ShowDestroyAtEnd = true
    },
    new UMLSequenceParticipant
    {
        ID = "SessionManager",
        Content = "SessionManager",
        IsActor = false
    }
};

// Create Messages
var messages = new MessageCollection
{
    new UMLSequenceMessage
    {
        ID = "MSG1",
        Content = "Login Request",
        FromParticipantID = "User",
        ToParticipantID = "System",
        Type = UMLSequenceMessageType.Synchronous
    },
    new UMLSequenceMessage
    {
        ID = "MSG2",
        Content = "Login Response",
        FromParticipantID = "System",
        ToParticipantID = "User",
        Type = UMLSequenceMessageType.Reply
    },
    new UMLSequenceMessage
    {
        ID = "MSG3",
        Content = "Log Event",
        FromParticipantID = "System",
        ToParticipantID = "Logger",
        Type = UMLSequenceMessageType.Asynchronous
    },
    new UMLSequenceMessage
    {
        ID = "MSG4",
        Content = "Create Session",
        FromParticipantID = "System",
        ToParticipantID = "SessionManager",
        Type = UMLSequenceMessageType.Create
    },
    new UMLSequenceMessage
    {
        ID = "MSG5",
        Content = "Delete Session",
        FromParticipantID = "System",
        ToParticipantID = "SessionManager",
        Type = UMLSequenceMessageType.Delete
    },
    new UMLSequenceMessage
    {
        ID = "MSG6",
        Content = "Validate Inputs",
        FromParticipantID = "System",
        ToParticipantID = "System",
        Type = UMLSequenceMessageType.Self
    }
};

// Initialize Diagram
SfDiagram Diagram = new SfDiagram();

 // Add participants and messages to the model
 Diagram.Model = new UMLSequenceDiagramModel
{
    Participants = participants,
    Messages = messages
};
{% endhighlight %}
{% endtabs %}

![Message Example](UML_SequenceDiagram_Images\MessagesExample.png)

#### Message Properties

| Property | Type | Description |
|---|---|---|
| ID | object | A unique identifier for the message |
| Content | string | The display text for the message |
| FromParticipantID | object | ID of the participant sending the message |
| ToParticipantID | object | ID of the participant receiving the message |
| Type | UMLSequenceMessageType | Type of the message (Synchronous, Asynchronous, Reply, Create, Delete, Self) |

### Activation Boxes

Activation boxes represent periods when a participant is active and processing a message. They appear as thin rectangles on participant lifelines.

#### Creating Activation Boxes

To create activation boxes in your sequence diagram:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDiagram x:Name="Diagram">
    <syncfusion:SfDiagram.Model>
        <syncfusion:UMLSequenceDiagramModel>
            <syncfusion:UMLSequenceDiagramModel.Participants>
                <syncfusion:ParticipantCollection>
                    <!-- A human-shaped participant-->
                    <syncfusion:UMLSequenceParticipant ID="User" 
                                        Content="User" 
                                        IsActor="true" />
                    <!-- A rectangle-shaped participant -->
                    <syncfusion:UMLSequenceParticipant ID="System" 
                                        Content="System" 
                                        IsActor="false" ShowDestroyAtEnd="True">
                        <syncfusion:UMLSequenceParticipant.ActivationBoxes>
                            <syncfusion:ActivationBoxCollection>
                                <syncfusion:UMLSequenceActivationBox ID="ActivateSystem" 
                                        StartMessageID="MSG1" 
                                        EndMessageID="MSG2" />
                            </syncfusion:ActivationBoxCollection>
                        </syncfusion:UMLSequenceParticipant.ActivationBoxes>
                    </syncfusion:UMLSequenceParticipant>
                </syncfusion:ParticipantCollection>
            </syncfusion:UMLSequenceDiagramModel.Participants>
            <syncfusion:UMLSequenceDiagramModel.Messages>
                <syncfusion:MessageCollection>
                    <!-- Synchronous message -->
                    <syncfusion:UMLSequenceMessage ID="MSG1" 
                                    Content="Login Request" 
                                    FromParticipantID="User" 
                                    ToParticipantID="System" 
                                    Type="Synchronous" />
                    <!-- Reply message -->
                    <syncfusion:UMLSequenceMessage ID="MSG2" 
                                    Content="Login Response" 
                                    FromParticipantID="System" 
                                    ToParticipantID="User" 
                                    Type="Reply" />
                </syncfusion:MessageCollection>
            </syncfusion:UMLSequenceDiagramModel.Messages>
        </syncfusion:UMLSequenceDiagramModel>
    </syncfusion:SfDiagram.Model>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}
// Create Participants with Activation Boxes
var participants = new ParticipantCollection
{
    new UMLSequenceParticipant
    {
        ID = "User",
        Content = "User",
        IsActor = true
    },
    new UMLSequenceParticipant
    {
        ID = "System",
        Content = "System",
        IsActor = false,
        ShowDestroyAtEnd = true,
        ActivationBoxes = new List<UMLSequenceActivationBox>
        {
            new UMLSequenceActivationBox
            {
                ID = "ActSystem",
                StartMessageID = "MSG1",
                EndMessageID = "MSG2"
            }
        }
    }
};

// Create Messages
var messages = new MessageCollection
{
    new UMLSequenceMessage
    {
        ID = "MSG1",
        Content = "Login Request",
        FromParticipantID = "User",
        ToParticipantID = "System",
        Type = UMLSequenceMessageType.Synchronous
    },
    new UMLSequenceMessage
    {
        ID = "MSG2",
        Content = "Login Response",
        FromParticipantID = "System",
        ToParticipantID = "User",
        Type = UMLSequenceMessageType.Reply
    }
};

// Intialize Diagram
SfDiagram Diagram = new SfDiagram();

// Update Participants and Messages to the Model
Diagram.Model = new UMLSequenceDiagramModel()
{
    Participants = participants,
    Messages = messages
};
{% endhighlight %}
{% endtabs %}

![Activations Example](UML_SequenceDiagram_Images\ActivationsExample.png)

#### Activation Box Properties

| Property | Type | Description |
|---|---|---|
| ID | object | A unique identifier for the activation box |
| StartMessageID | object | ID of the message that initiates the activation |
| EndMessageID | object | ID of the message that terminates the activation |

### Fragments

Fragments group a set of messages based on specific conditions in a sequence diagram. They are displayed as rectangular enclosures that visually separate conditional or looping interactions.

#### Types of Fragments

The `UMLSequenceFragmentType` enum defines the following fragment types:

Here is the updated table with precise descriptions and correct usage:  

| Fragment Type  | Description  | Usage  |  
|---------------|-------------|--------|  
| Optional  | Represents a sequence that is executed only if a specified condition is met; otherwise, it is skipped. | ![Optional Fragment](UML_SequenceDiagram_Images\OptFragment.png) |  
| Alternative | Represents multiple conditional paths (if-else structure), where only one path executes based on the condition. | ![Alternative Fragment](UML_SequenceDiagram_Images\AltFragment.png) |  
| Loop | Represents a repeating sequence of interactions that continues based on a loop condition. | ![Loop Fragment](UML_SequenceDiagram_Images\LoopFragment.png) |  

#### Creating Fragments

To create fragments in your sequence diagram:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDiagram x:Name="Diagram">
    <syncfusion:SfDiagram.Model>
        <syncfusion:UMLSequenceDiagramModel SpaceBetweenParticipants="300">

            <!-- Define Participants -->
            <syncfusion:UMLSequenceDiagramModel.Participants>
                <syncfusion:ParticipantCollection>
                    <!-- Customer initiates the order -->
                    <syncfusion:UMLSequenceParticipant ID="Customer" Content="Customer" IsActor="True" />

                    <!-- Order Processing System -->
                    <syncfusion:UMLSequenceParticipant ID="OrderSystem" Content="Order System" IsActor="False" />

                    <!-- Payment Gateway -->
                    <syncfusion:UMLSequenceParticipant ID="PaymentGateway" Content="Payment Gateway" IsActor="False" />
                </syncfusion:ParticipantCollection>
            </syncfusion:UMLSequenceDiagramModel.Participants>

            <!-- Define Messages -->
            <syncfusion:UMLSequenceDiagramModel.Messages>
                <syncfusion:MessageCollection>
                    <!-- Customer places an order -->
                    <syncfusion:UMLSequenceMessage ID="MSG1" 
                                            Content="Place Order" 
                                            FromParticipantID="Customer" 
                                            ToParticipantID="OrderSystem" 
                                            Type="Synchronous" />

                    <!-- System checks if the item is in stock -->
                    <syncfusion:UMLSequenceMessage ID="MSG2" 
                                            Content="Check Stock Availability" 
                                            FromParticipantID="OrderSystem" 
                                            ToParticipantID="OrderSystem" 
                                            Type="Synchronous" />

                    <!-- System confirms stock is available -->
                    <syncfusion:UMLSequenceMessage ID="MSG3" 
                                            Content="Stock Available" 
                                            FromParticipantID="OrderSystem" 
                                            ToParticipantID="Customer" 
                                            Type="Reply" />

                    <!-- System requests payment processing -->
                    <syncfusion:UMLSequenceMessage ID="MSG4" 
                                            Content="Process Payment" 
                                            FromParticipantID="OrderSystem" 
                                            ToParticipantID="PaymentGateway" 
                                            Type="Synchronous" />

                    <!-- Payment success message -->
                    <syncfusion:UMLSequenceMessage ID="MSG5" 
                                            Content="Payment Successful" 
                                            FromParticipantID="PaymentGateway" 
                                            ToParticipantID="OrderSystem" 
                                            Type="Reply" />

                    <!-- System confirms order processing -->
                    <syncfusion:UMLSequenceMessage ID="MSG6" 
                                            Content="Order Confirmed and Shipped" 
                                            FromParticipantID="OrderSystem" 
                                            ToParticipantID="Customer" 
                                            Type="Reply" />

                    <!-- Payment failure message -->
                    <syncfusion:UMLSequenceMessage ID="MSG7" 
                                            Content="Payment Failed" 
                                            FromParticipantID="PaymentGateway" 
                                            ToParticipantID="OrderSystem" 
                                            Type="Reply" />

                    <!-- Retry payment message -->
                    <syncfusion:UMLSequenceMessage ID="MSG8" 
                                            Content="Retry Payment" 
                                            FromParticipantID="OrderSystem" 
                                            ToParticipantID="Customer" 
                                            Type="Reply" />
                </syncfusion:MessageCollection>
            </syncfusion:UMLSequenceDiagramModel.Messages>
            <!-- Define Fragments -->
            <syncfusion:UMLSequenceDiagramModel.Fragments>
                <syncfusion:FragmentCollection>
                    <!-- Loop Fragment: Retry payment attempts -->
                    <syncfusion:UMLSequenceFragment ID="Frag3" Type="Loop">
                        <syncfusion:UMLSequenceFragment.Conditions>
                            <syncfusion:ConditionCollection>
                                <syncfusion:UMLSequenceFragmentCondition Content="while attempts less than 3">
                                    <!--Nested Fragments Inside Loop Fragment-->
                                    <syncfusion:UMLSequenceFragmentCondition.Fragments>
                                        <syncfusion:FragmentCollection>
                                            <!-- Optional Fragment: Only executes if item is in stock -->
                                            <syncfusion:UMLSequenceFragment ID="Frag1" Type="Optional">
                                                <syncfusion:UMLSequenceFragment.Conditions>
                                                    <syncfusion:ConditionCollection>
                                                        <syncfusion:UMLSequenceFragmentCondition Content="if item is in stock">
                                                            <syncfusion:UMLSequenceFragmentCondition.MessageIds>
                                                                <syncfusion:MessageIdCollection>
                                                                    <sys:String>MSG4</sys:String>
                                                                </syncfusion:MessageIdCollection>
                                                            </syncfusion:UMLSequenceFragmentCondition.MessageIds>
                                                        </syncfusion:UMLSequenceFragmentCondition>
                                                    </syncfusion:ConditionCollection>
                                                </syncfusion:UMLSequenceFragment.Conditions>
                                            </syncfusion:UMLSequenceFragment>
                                            <!-- Alternative Fragment: Payment success or failure -->
                                            <syncfusion:UMLSequenceFragment ID="Frag2" Type="Alternative">
                                                <syncfusion:UMLSequenceFragment.Conditions>
                                                    <syncfusion:ConditionCollection>
                                                        <!-- If payment is successful -->
                                                        <syncfusion:UMLSequenceFragmentCondition Content="if payment is successful">
                                                            <syncfusion:UMLSequenceFragmentCondition.MessageIds>
                                                                <syncfusion:MessageIdCollection>
                                                                    <sys:String>MSG5</sys:String>
                                                                    <sys:String>MSG6</sys:String>
                                                                </syncfusion:MessageIdCollection>
                                                            </syncfusion:UMLSequenceFragmentCondition.MessageIds>
                                                        </syncfusion:UMLSequenceFragmentCondition>

                                                        <!-- If payment fails -->
                                                        <syncfusion:UMLSequenceFragmentCondition Content="if payment fails">
                                                            <syncfusion:UMLSequenceFragmentCondition.MessageIds>
                                                                <syncfusion:MessageIdCollection>
                                                                    <sys:String>MSG7</sys:String>
                                                                    <sys:String>MSG8</sys:String>
                                                                </syncfusion:MessageIdCollection>
                                                            </syncfusion:UMLSequenceFragmentCondition.MessageIds>
                                                        </syncfusion:UMLSequenceFragmentCondition>
                                                    </syncfusion:ConditionCollection>
                                                </syncfusion:UMLSequenceFragment.Conditions>
                                            </syncfusion:UMLSequenceFragment>
                                        </syncfusion:FragmentCollection>
                                    </syncfusion:UMLSequenceFragmentCondition.Fragments>
                                </syncfusion:UMLSequenceFragmentCondition>
                            </syncfusion:ConditionCollection>
                        </syncfusion:UMLSequenceFragment.Conditions>
                    </syncfusion:UMLSequenceFragment>
                </syncfusion:FragmentCollection>
            </syncfusion:UMLSequenceDiagramModel.Fragments>
        </syncfusion:UMLSequenceDiagramModel>
    </syncfusion:SfDiagram.Model>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}
// Define Participants
var participants = new ParticipantCollection
{
    new UMLSequenceParticipant { ID = "Customer", Content = "Customer", IsActor = true },
    new UMLSequenceParticipant { ID = "OrderSystem", Content = "Order System", IsActor = false },
    new UMLSequenceParticipant { ID = "PaymentGateway", Content = "Payment Gateway", IsActor = false }
};

// Define Messages
var messages = new MessageCollection
{
    new UMLSequenceMessage { ID = "MSG1", Content = "Place Order", FromParticipantID = "Customer", ToParticipantID = "OrderSystem", Type = UMLSequenceMessageType.Synchronous },
    new UMLSequenceMessage { ID = "MSG2", Content = "Check Stock Availability", FromParticipantID = "OrderSystem", ToParticipantID = "OrderSystem", Type = UMLSequenceMessageType.Synchronous },
    new UMLSequenceMessage { ID = "MSG3", Content = "Stock Available", FromParticipantID = "OrderSystem", ToParticipantID = "Customer", Type = UMLSequenceMessageType.Reply },
    new UMLSequenceMessage { ID = "MSG4", Content = "Process Payment", FromParticipantID = "OrderSystem", ToParticipantID = "PaymentGateway", Type = UMLSequenceMessageType.Synchronous },
    new UMLSequenceMessage { ID = "MSG5", Content = "Payment Successful", FromParticipantID = "PaymentGateway", ToParticipantID = "OrderSystem", Type = UMLSequenceMessageType.Reply },
    new UMLSequenceMessage { ID = "MSG6", Content = "Order Confirmed and Shipped", FromParticipantID = "OrderSystem", ToParticipantID = "Customer", Type = UMLSequenceMessageType.Reply },
    new UMLSequenceMessage { ID = "MSG7", Content = "Payment Failed", FromParticipantID = "PaymentGateway", ToParticipantID = "OrderSystem", Type = UMLSequenceMessageType.Reply },
    new UMLSequenceMessage { ID = "MSG8", Content = "Retry Payment", FromParticipantID = "OrderSystem", ToParticipantID = "Customer", Type = UMLSequenceMessageType.Reply }
};

// Define Fragments
var fragments = new FragmentCollection
{
    // Loop Fragment: Retry payment attempts
    new UMLSequenceFragment
    {
        ID = 3,
        Type = UMLSequenceFragmentType.Loop,
        Conditions = new ConditionCollection
        {
            new UMLSequenceFragmentCondition
            {
                Content = "while attempts less than 3",
                Fragments = new List<UMLSequenceFragment>
                {
                    // Optional Fragment: Only executes if item is in stock
                    new UMLSequenceFragment
                    {
                        ID = 1,
                        Type = UMLSequenceFragmentType.Optional,
                        Conditions = new ConditionCollection
                        {
                            new UMLSequenceFragmentCondition
                            {
                                Content = "if item is in stock",
                                MessageIds = new MessageIdCollection { "MSG4" }
                            }
                        }
                    },

                    // Alternative Fragment: Payment success or failure
                    new UMLSequenceFragment
                    {
                        ID = 2,
                        Type = UMLSequenceFragmentType.Alternative,
                        Conditions = new ConditionCollection
                        {
                            new UMLSequenceFragmentCondition
                            {
                                Content = "if payment is successful",
                                MessageIds = new MessageIdCollection { "MSG5", "MSG6" }
                            },
                            new UMLSequenceFragmentCondition
                            {
                                Content = "if payment fails",
                                MessageIds = new MessageIdCollection { "MSG7", "MSG8" }
                            }
                        }
                    }
                }
            }
        }
    }
};


// Intialize Diagram
SfDiagram Diagram = new SfDiagram();

// Update Participants, Messages and Fragments to the Model
Diagram.Model = new UMLSequenceDiagramModel()
{
    SpaceBetweenParticipants = 300,
    Participants = participants,
    Messages = messages,
    Fragments = fragments
};
{% endhighlight %}
{% endtabs %}

![Fragment Example](UML_SequenceDiagram_Images\FragmentsExample.png)

#### Fragment Properties

| Property | Type | Description |
|---|---|---|
| ID | object | A unique identifier for the fragment |
| Type | UMLSequenceFragmentType | Type of the fragment (Optional, Loop, Alternative) |
| Conditions | IEnumerable\<UMLSequenceFragmentCondition\> | Collection of conditions for the fragment |

#### Fragment Condition Properties

| Property | Type | Description |
|---|---|---|
| Content | string | Text describing the condition or parameter |
| MessageIds | IEnumerable\<object\> | Collection of message IDs included in this condition section |
| Fragments | IEnumerable\<UMLSequenceFragment\> | Collection of nested fragments (for complex structures) |

### Customizing Participant Spacing in Sequence Diagram 

The `SpaceBetweenParticipants` property in `UMLSequenceDiagramModel` controls the horizontal gap between participants. The default value is 100, but you can adjust it as needed.  

{% tabs %}  
{% highlight xaml %}
{% endhighlight %}  
<syncfusion:SfDiagram x:Name="Diagram">
    <syncfusion:SfDiagram.Model>
        <syncfusion:UMLSequenceDiagramModel SpaceBetweenParticipants="300">
            
            <!-- Define Participants -->
            <syncfusion:UMLSequenceDiagramModel.Participants>
                <syncfusion:ParticipantCollection>
                    <!-- Add participants here -->
                </syncfusion:ParticipantCollection>
            </syncfusion:UMLSequenceDiagramModel.Participants>

            <!-- Define Messages -->
            <syncfusion:UMLSequenceDiagramModel.Messages>
                <syncfusion:MessageCollection>
                    <!-- Add messages here -->
                </syncfusion:MessageCollection>
            </syncfusion:UMLSequenceDiagramModel.Messages>

        </syncfusion:UMLSequenceDiagramModel>
    </syncfusion:SfDiagram.Model>
</syncfusion:SfDiagram>
{% highlight c# %}  
// Intialize Diagram
SfDiagram Diagram = new SfDiagram();

// Initialize the sequence diagram model with custom spacing and predefined elements  
Diagram.Model = new UMLSequenceDiagramModel()  
{  
    SpaceBetweenParticipants = 300, // Sets the horizontal spacing between participants (default is 100)  
    Participants = participants,    // List of participants in the sequence diagram  
    Messages = messages,            // List of messages exchanged between participants  
    Fragments = fragments           // List of sequence diagram fragments (opt, alt, loop)  
};
{% endhighlight %}  
{% endtabs %}  
