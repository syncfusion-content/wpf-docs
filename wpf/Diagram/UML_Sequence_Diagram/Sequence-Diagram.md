---
layout: post
title: Sequence Diagram Model in WPF Diagram control | Syncfusion®
description: Learn here all about Sequence Diagram Model support in Syncfusion® WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Sequence Diagram Model in WPF Diagram (SfDiagram)

A sequence diagram is an interaction diagram that shows how objects operate with one another and in what order. The WPF Diagram (SfDiagram) control provides comprehensive support for creating and visualizing UML sequence diagrams through the `UMLSequenceDiagramModel` class.

## Creating a Sequence Diagram

To create a sequence diagram using the SfDiagram control, follow these steps:

1. Create an instance of `SfDiagram`
2. Create a `UMLSequenceDiagramModel` and assign it to the diagram's Model property
3. Define participants, messages, activation boxes, and fragments
4. Call the `UpdateUMLSequenceDiagram` method to render the diagram

{% tabs %}
{% highlight xaml %}
<!-- Initialize the SfDiagram with UMLSequenceDiagramModel -->
<syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Model>
        <syncfusion:UMLSequenceDiagramModel SpaceBetweenParticipants="120">
            <!-- Participants will be defined here -->
            <syncfusion:UMLSequenceDiagramModel.Participants>
                <syncfusion:ParticipantCollection>
                    <!-- Participant definitions -->
                </syncfusion:ParticipantCollection>
            </syncfusion:UMLSequenceDiagramModel.Participants>
            
            <!-- Messages will be defined here -->
            <syncfusion:UMLSequenceDiagramModel.Messages>
                <syncfusion:MessageCollection>
                    <!-- Message definitions -->
                </syncfusion:MessageCollection>
            </syncfusion:UMLSequenceDiagramModel.Messages>
            
            <!-- Fragments will be defined here -->
            <syncfusion:UMLSequenceDiagramModel.Fragments>
                <syncfusion:FragmentCollection>
                    <!-- Fragment definitions -->
                </syncfusion:FragmentCollection>
            </syncfusion:UMLSequenceDiagramModel.Fragments>
        </syncfusion:UMLSequenceDiagramModel>
    </syncfusion:SfDiagram.Model>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}
// Initialize the diagram
SfDiagram diagram = new SfDiagram();

// Create a sequence diagram model
UMLSequenceDiagramModel model = new UMLSequenceDiagramModel();

// Set the spacing between participants (optional)
model.SpaceBetweenParticipants = 120;

// Define participants, messages, and fragments
// (code for these definitions will be shown in the following sections)

// Assign the model to the diagram
diagram.Model = model;
{% endhighlight %}
{% endtabs %}

## Sequence Diagram Elements

A sequence diagram consists of several key elements: participants, messages, activation boxes, and fragments. Let's explore each of these in detail.

### Participants

Participants represent objects or actors in the sequence diagram. They appear at the top of the diagram with lifelines extending vertically downward.

#### Types of Participants

The `UMLSequenceParticipant` class offers two types of participants:

1. **Actors**: Human users or external systems (set `IsActor = true`)
2. **Lifelines**: Software components or objects (set `IsActor = false`)

#### Creating Participants

To create participants in your sequence diagram:

{% tabs %}
{% highlight xaml %}
<syncfusion:UMLSequenceDiagramModel.Participants>
    <syncfusion:ParticipantCollection>
        <!-- An actor participant -->
        <syncfusion:UMLSequenceParticipant ID="User" 
                                          Content="User" 
                                          IsActor="true" />
        
        <!-- A lifeline participant -->
        <syncfusion:UMLSequenceParticipant ID="System" 
                                          Content="System" 
                                          IsActor="false" />
    </syncfusion:ParticipantCollection>
</syncfusion:UMLSequenceDiagramModel.Participants>
{% endhighlight %}

{% highlight c# %}
// Create participants
List<UMLSequenceParticipant> participants = new List<UMLSequenceParticipant>
{
    // Create an actor participant
    new UMLSequenceParticipant
    {
        ID = "User",            // Unique identifier for the participant
        Content = "User",       // Display text
        IsActor = true          // Set to true for actor, false for lifeline
    },
    
    // Create a lifeline participant
    new UMLSequenceParticipant
    {
        ID = "System",
        Content = "System",
        IsActor = false,
        ShowDestroyAtEnd = true  // Optional: Show destruction marker at end
    }
};

// Add participants to the model
model.Participants = participants;
{% endhighlight %}
{% endtabs %}

#### Participant Properties

| Property | Type | Description |
|---|---|---|
| ID | object | Unique identifier for the participant |
| Content | string | The display text for the participant |
| IsActor | bool | Determines if the participant is displayed as an actor (true) or lifeline (false) |
| ShowDestroyAtEnd | bool | Determines if a destruction marker (X) is shown at the end of the lifeline |
| ActivationBoxes | IEnumerable\<UMLSequenceActivationBox\> | Collection of activation boxes for this participant |

### Messages

Messages represent communication between participants and are displayed as arrows connecting lifelines.

#### Types of Messages

The `UMLSequenceMessageType` enum defines the following message types:

| Message Type | Description | Visual Representation |
|---|---|---|
| Synchronous | The sender waits for a response | Solid line with filled arrowhead |
| Asynchronous | The sender continues without waiting | Solid line with open arrowhead |
| Reply | A response to a previous message | Dashed line with open arrowhead |
| Create | Creates a new participant | Dashed line with open arrowhead (to newly created object) |
| Delete | Terminates a participant | Solid line with X at the end (receiver is destroyed) |
| Self | A message from a participant to itself | Curved line from and to the same lifeline |

#### Creating Messages

To create messages in your sequence diagram:

{% tabs %}
{% highlight xaml %}
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
{% endhighlight %}

{% highlight c# %}
// Create messages
List<UMLSequenceMessage> messages = new List<UMLSequenceMessage>
{
    // Synchronous message
    new UMLSequenceMessage
    {
        ID = "MSG1",                   // Unique identifier for the message
        Content = "Login Request",     // Message text
        FromParticipantID = "User",    // ID of the sending participant
        ToParticipantID = "System",    // ID of the receiving participant
        Type = UMLSequenceMessageType.Synchronous
    },
    
    // Reply message
    new UMLSequenceMessage
    {
        ID = "MSG2",
        Content = "Login Response",
        FromParticipantID = "System",
        ToParticipantID = "User",
        Type = UMLSequenceMessageType.Reply
    },
    
    // Self message
    new UMLSequenceMessage
    {
        ID = "MSG3",
        Content = "Process Data",
        FromParticipantID = "System",
        ToParticipantID = "System",
        Type = UMLSequenceMessageType.Self
    }
};

// Add messages to the model
model.Messages = messages;
{% endhighlight %}
{% endtabs %}

#### Message Properties

| Property | Type | Description |
|---|---|---|
| ID | object | Unique identifier for the message |
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
<syncfusion:UMLSequenceParticipant ID="System" Content="System" IsActor="false">
    <syncfusion:UMLSequenceParticipant.ActivationBoxes>
        <syncfusion:ActivationBoxCollection>
            <syncfusion:UMLSequenceActivationBox ID="ActSystem" 
                                               StartMessageID="MSG1" 
                                               EndMessageID="MSG2" />
        </syncfusion:ActivationBoxCollection>
    </syncfusion:UMLSequenceParticipant.ActivationBoxes>
</syncfusion:UMLSequenceParticipant>
{% endhighlight %}

{% highlight c# %}
// Create participants with activation boxes
List<UMLSequenceParticipant> participants = new List<UMLSequenceParticipant>
{
    new UMLSequenceParticipant
    {
        ID = "User",
        Content = "User",
        IsActor = true,
        ActivationBoxes = new List<UMLSequenceActivationBox>
        {
            new UMLSequenceActivationBox
            {
                ID = "ActUser",
                StartMessageID = "MSG1",
                EndMessageID = "MSG2"
            }
        }
    },
    new UMLSequenceParticipant
    {
        ID = "System",
        Content = "System",
        IsActor = false,
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

// Add participants to the model
model.Participants = participants;
{% endhighlight %}
{% endtabs %}

#### Activation Box Properties

| Property | Type | Description |
|---|---|---|
| ID | object | Unique identifier for the activation box |
| StartMessageID | object | ID of the message that initiates the activation |
| EndMessageID | object | ID of the message that terminates the activation |

### Fragments

Fragments group messages together and apply control structures like conditions, loops, and alternatives. They are displayed as rectangles enclosing a section of the sequence diagram.

#### Types of Fragments

The `UMLSequenceFragmentType` enum defines the following fragment types:

| Fragment Type | Description | Usage |
|---|---|---|
| Optional (opt) | Shows an optional sequence that executes only if a condition is true | Single condition section |
| Alternative (alt) | Shows different paths based on conditions (if-else structure) | Multiple condition sections |
| Loop | Shows a repeating sequence | Single condition section with a loop guard |

#### Creating Fragments

To create fragments in your sequence diagram:

{% tabs %}
{% highlight xaml %}
<syncfusion:UMLSequenceDiagramModel.Fragments>
    <syncfusion:FragmentCollection>
        <!-- Optional fragment -->
        <syncfusion:UMLSequenceFragment ID="Frag1" Type="Optional">
            <syncfusion:UMLSequenceFragment.Conditions>
                <syncfusion:ConditionCollection>
                    <syncfusion:UMLSequenceFragmentCondition Content="[if user exists]">
                        <syncfusion:UMLSequenceFragmentCondition.MessageIds>
                            <syncfusion:MessageIdCollection>
                                <sys:String>MSG3</sys:String>
                            </syncfusion:MessageIdCollection>
                        </syncfusion:UMLSequenceFragmentCondition.MessageIds>
                    </syncfusion:UMLSequenceFragmentCondition>
                </syncfusion:ConditionCollection>
            </syncfusion:UMLSequenceFragment.Conditions>
        </syncfusion:UMLSequenceFragment>
        
        <!-- Alternative fragment (if-else) -->
        <syncfusion:UMLSequenceFragment ID="Frag2" Type="Alternative">
            <syncfusion:UMLSequenceFragment.Conditions>
                <syncfusion:ConditionCollection>
                    <!-- If condition -->
                    <syncfusion:UMLSequenceFragmentCondition Content="[valid credentials]">
                        <syncfusion:UMLSequenceFragmentCondition.MessageIds>
                            <syncfusion:MessageIdCollection>
                                <sys:String>MSG4</sys:String>
                            </syncfusion:MessageIdCollection>
                        </syncfusion:UMLSequenceFragmentCondition.MessageIds>
                    </syncfusion:UMLSequenceFragmentCondition>
                    <!-- Else condition -->
                    <syncfusion:UMLSequenceFragmentCondition Content="[else]">
                        <syncfusion:UMLSequenceFragmentCondition.MessageIds>
                            <syncfusion:MessageIdCollection>
                                <sys:String>MSG5</sys:String>
                            </syncfusion:MessageIdCollection>
                        </syncfusion:UMLSequenceFragmentCondition.MessageIds>
                    </syncfusion:UMLSequenceFragmentCondition>
                </syncfusion:ConditionCollection>
            </syncfusion:UMLSequenceFragment.Conditions>
        </syncfusion:UMLSequenceFragment>
    </syncfusion:FragmentCollection>
</syncfusion:UMLSequenceDiagramModel.Fragments>
{% endhighlight %}

{% highlight c# %}
// Create fragments
List<UMLSequenceFragment> fragments = new List<UMLSequenceFragment>
{
    // Optional fragment
    new UMLSequenceFragment
    {
        ID = 1,
        Type = UMLSequenceFragmentType.Optional,
        Conditions = new List<UMLSequenceFragmentCondition>
        {
            new UMLSequenceFragmentCondition
            {
                Content = "[if user exists]",
                MessageIds = new List<object> { "MSG3" }
            }
        }
    },
    
    // Alternative fragment (if-else)
    new UMLSequenceFragment
    {
        ID = 2,
        Type = UMLSequenceFragmentType.Alternative,
        Conditions = new List<UMLSequenceFragmentCondition>
        {
            // If condition
            new UMLSequenceFragmentCondition
            {
                Content = "[valid credentials]",
                MessageIds = new List<object> { "MSG4" }
            },
            // Else condition
            new UMLSequenceFragmentCondition
            {
                Content = "[else]",
                MessageIds = new List<object> { "MSG5" }
            }
        }
    },
    
    // Loop fragment
    new UMLSequenceFragment
    {
        ID = 3,
        Type = UMLSequenceFragmentType.Loop,
        Conditions = new List<UMLSequenceFragmentCondition>
        {
            new UMLSequenceFragmentCondition
            {
                Content = "[for each item]",
                MessageIds = new List<object> { "MSG6", "MSG7" }
            }
        }
    }
};

// Add fragments to the model
model.Fragments = fragments;
{% endhighlight %}
{% endtabs %}

#### Fragment Properties

| Property | Type | Description |
|---|---|---|
| ID | object | Unique identifier for the fragment |
| Type | UMLSequenceFragmentType | Type of the fragment (Optional, Loop, Alternative) |
| Conditions | IEnumerable\<UMLSequenceFragmentCondition\> | Collection of conditions for the fragment |

#### Fragment Condition Properties

| Property | Type | Description |
|---|---|---|
| Content | string | Text describing the condition or guard |
| MessageIds | IEnumerable\<object\> | Collection of message IDs included in this condition section |
| Fragments | IEnumerable\<UMLSequenceFragment\> | Collection of nested fragments (for complex structures) |

## Step-by-Step Guide to Creating a Sequence Diagram

Let's create a complete sequence diagram that demonstrates a login interaction between a user and a system:

### Step 1: Create and Configure the SfDiagram

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Model>
        <syncfusion:UMLSequenceDiagramModel SpaceBetweenParticipants="120"/>
    </syncfusion:SfDiagram.Model>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}
// Initialize the diagram
SfDiagram diagram = new SfDiagram();

// Create the sequence diagram model
UMLSequenceDiagramModel model = new UMLSequenceDiagramModel
{
    SpaceBetweenParticipants = 120
};

// Assign the model to the diagram
diagram.Model = model;
{% endhighlight %}
{% endtabs %}

### Step 2: Define Participants

{% tabs %}
{% highlight c# %}
// Create participants
List<UMLSequenceParticipant> participants = new List<UMLSequenceParticipant>
{
    // User (Actor)
    new UMLSequenceParticipant
    {
        ID = "User",
        Content = "User",
        IsActor = true,
        ActivationBoxes = new List<UMLSequenceActivationBox>
        {
            new UMLSequenceActivationBox
            {
                ID = "ActUser1",
                StartMessageID = "MSG1",
                EndMessageID = "MSG2"
            }
        }
    },
    
    // Authentication Service (Lifeline)
    new UMLSequenceParticipant
    {
        ID = "Auth",
        Content = "Authentication Service",
        IsActor = false,
        ActivationBoxes = new List<UMLSequenceActivationBox>
        {
            new UMLSequenceActivationBox
            {
                ID = "ActAuth1",
                StartMessageID = "MSG1",
                EndMessageID = "MSG2"
            },
            new UMLSequenceActivationBox
            {
                ID = "ActAuth2",
                StartMessageID = "MSG3",
                EndMessageID = "MSG3"
            }
        }
    },
    
    // Database (Lifeline)
    new UMLSequenceParticipant
    {
        ID = "DB",
        Content = "Database",
        IsActor = false,
        ActivationBoxes = new List<UMLSequenceActivationBox>
        {
            new UMLSequenceActivationBox
            {
                ID = "ActDB1",
                StartMessageID = "MSG4",
                EndMessageID = "MSG5"
            }
        }
    }
};

// Add participants to the model
model.Participants = participants;
{% endhighlight %}
{% endtabs %}

### Step 3: Define Messages

{% tabs %}
{% highlight c# %}
// Create messages
List<UMLSequenceMessage> messages = new List<UMLSequenceMessage>
{
    // User sends login request
    new UMLSequenceMessage
    {
        ID = "MSG1",
        Content = "Login(username, password)",
        FromParticipantID = "User",
        ToParticipantID = "Auth",
        Type = UMLSequenceMessageType.Synchronous
    },
    
    // Authentication service self-processes
    new UMLSequenceMessage
    {
        ID = "MSG3",
        Content = "ValidateInput()",
        FromParticipantID = "Auth",
        ToParticipantID = "Auth",
        Type = UMLSequenceMessageType.Self
    },
    
    // Authentication service checks database
    new UMLSequenceMessage
    {
        ID = "MSG4",
        Content = "CheckCredentials(username, password)",
        FromParticipantID = "Auth",
        ToParticipantID = "DB",
        Type = UMLSequenceMessageType.Synchronous
    },
    
    // Database returns result
    new UMLSequenceMessage
    {
        ID = "MSG5",
        Content = "Return result",
        FromParticipantID = "DB",
        ToParticipantID = "Auth",
        Type = UMLSequenceMessageType.Reply
    },
    
    // Authentication service returns login success
    new UMLSequenceMessage
    {
        ID = "MSG6",
        Content = "Login Success",
        FromParticipantID = "Auth",
        ToParticipantID = "User",
        Type = UMLSequenceMessageType.Reply
    },
    
    // Authentication service returns login failure
    new UMLSequenceMessage
    {
        ID = "MSG7",
        Content = "Login Failed",
        FromParticipantID = "Auth",
        ToParticipantID = "User",
        Type = UMLSequenceMessageType.Reply
    },
    
    // Final response message (success or failure)
    new UMLSequenceMessage
    {
        ID = "MSG2",
        Content = "Return response",
        FromParticipantID = "Auth",
        ToParticipantID = "User",
        Type = UMLSequenceMessageType.Reply
    }
};

// Add messages to the model
model.Messages = messages;
{% endhighlight %}
{% endtabs %}

### Step 4: Define Fragments

{% tabs %}
{% highlight c# %}
// Create fragments
List<UMLSequenceFragment> fragments = new List<UMLSequenceFragment>
{
    // Optional fragment for input validation
    new UMLSequenceFragment
    {
        ID = 1,
        Type = UMLSequenceFragmentType.Optional,
        Conditions = new List<UMLSequenceFragmentCondition>
        {
            new UMLSequenceFragmentCondition
            {
                Content = "opt [if input not empty]",
                MessageIds = new List<object> { "MSG3" }
            }
        }
    },
    
    // Alternative fragment for login result
    new UMLSequenceFragment
    {
        ID = 2,
        Type = UMLSequenceFragmentType.Alternative,
        Conditions = new List<UMLSequenceFragmentCondition>
        {
            // If credentials are valid
            new UMLSequenceFragmentCondition
            {
                Content = "alt [valid credentials]",
                MessageIds = new List<object> { "MSG6" }
            },
            // If credentials are invalid
            new UMLSequenceFragmentCondition
            {
                Content = "else [invalid credentials]",
                MessageIds = new List<object> { "MSG7" }
            }
        }
    },
    
    // Loop fragment (example for complex scenarios)
    new UMLSequenceFragment
    {
        ID = 3,
        Type = UMLSequenceFragmentType.Loop,
        Conditions = new List<UMLSequenceFragmentCondition>
        {
            new UMLSequenceFragmentCondition
            {
                Content = "loop [for retry attempts]",
                MessageIds = new List<object> { "MSG4", "MSG5" }
            }
        }
    }
};

// Add fragments to the model
model.Fragments = fragments;
{% endhighlight %}
{% endtabs %}

### Step 5: Update and Render the Diagram

{% tabs %}
{% highlight c# %}
// Create the complete model
UMLSequenceDiagramModel sequenceModel = new UMLSequenceDiagramModel
{
    SpaceBetweenParticipants = 120,
    Participants = participants,
    Messages = messages,
    Fragments = fragments
};

// Assign the model to the diagram
diagram.Model = sequenceModel;

// Update the diagram to render it
(diagram.Model as UMLSequenceDiagramModel).UpdateUMLSequenceDiagram();
{% endhighlight %}
{% endtabs %}

![Complete Sequence Diagram in WPF Diagram](Automatic-Layouts_images/wpf-diagram-complete-sequence-diagram.png)

## Customizing Diagram Layout

The `UMLSequenceDiagramModel` provides several properties to customize the layout of the sequence diagram:

{% tabs %}
{% highlight c# %}
// Customize the sequence diagram layout
UMLSequenceDiagramModel model = new UMLSequenceDiagramModel
{
    // Space between participants
    SpaceBetweenParticipants = 150,
    
    // Width of activation boxes
    // (Access through internal property, consider requesting API for this)
    // model.ActivationWidth = 20,
    
    // Initial length of lifelines
    // (Access through internal property, consider requesting API for this)
    // model.InitialLifelineLength = 100,
    
    // Vertical spacing between messages
    // (Access through internal property, consider requesting API for this)
    // model.MessageSpacing = 50
};
{% endhighlight %}
{% endtabs %}

## Mermaid Text Support

The `UMLSequenceDiagramModel` provides support for working with Mermaid text format, a popular text-based syntax for creating diagrams.

### Import from Mermaid

You can load a sequence diagram from Mermaid text format:

{% tabs %}
{% highlight c# %}
// Mermaid text representation of a sequence diagram
string mermaidText = @"sequenceDiagram
    User->>Auth: Login(username, password)
    Auth->>Auth: ValidateInput()
    Auth->>Database: CheckCredentials(username, password)
    Database-->>Auth: Return result
    
    alt valid credentials
        Auth-->>User: Login Success
    else invalid credentials
        Auth-->>User: Login Failed
    end";

// Create a sequence diagram model
UMLSequenceDiagramModel model = new UMLSequenceDiagramModel();

// Load the diagram from Mermaid text
// (Note: This method is internal and not part of the public API)
// model.LoadFromMermaid(mermaidText);

// Assign the model to the diagram
diagram.Model = model;

// Update the diagram to render it
(diagram.Model as UMLSequenceDiagramModel).UpdateUMLSequenceDiagram();
{% endhighlight %}
{% endtabs %}

### Export to Mermaid

You can export a sequence diagram to Mermaid text format:

{% tabs %}
{% highlight c# %}
// Create a sequence diagram (using steps from earlier examples)
UMLSequenceDiagramModel model = new UMLSequenceDiagramModel();
// ... (define participants, messages, fragments)

// Assign the model to the diagram
diagram.Model = model;

// Export diagram to Mermaid text
// (Note: This method is internal and not part of the public API)
// string mermaidText = model.ExportToMermaid();
// Console.WriteLine(mermaidText);
{% endhighlight %}
{% endtabs %}

## Complete Example

Here's a complete example that creates a sequence diagram showing a user authentication flow:

{% tabs %}
{% highlight xaml %}
<!-- Complete XAML example with all elements -->
<syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Model>
        <syncfusion:UMLSequenceDiagramModel SpaceBetweenParticipants="120">
            <!-- Define participants -->
            <syncfusion:UMLSequenceDiagramModel.Participants>
                <syncfusion:ParticipantCollection>
                    <!-- User actor -->
                    <syncfusion:UMLSequenceParticipant ID="User" Content="User" IsActor="true">
                        <syncfusion:UMLSequenceParticipant.ActivationBoxes>
                            <syncfusion:ActivationBoxCollection>
                                <syncfusion:UMLSequenceActivationBox ID="ActUser1" 
                                                                    StartMessageID="MSG1" 
                                                                    EndMessageID="MSG2" />
                            </syncfusion:ActivationBoxCollection>
                        </syncfusion:UMLSequenceParticipant.ActivationBoxes>
                    </syncfusion:UMLSequenceParticipant>
                    
                    <!-- Authentication Service -->
                    <syncfusion:UMLSequenceParticipant ID="Auth" Content="Authentication Service" IsActor="false">
                        <syncfusion:UMLSequenceParticipant.ActivationBoxes>
                            <syncfusion:ActivationBoxCollection>
                                <syncfusion:UMLSequenceActivationBox ID="ActAuth1" 
                                                                    StartMessageID="MSG1" 
                                                                    EndMessageID="MSG2" />
                                <syncfusion:UMLSequenceActivationBox ID="ActAuth2" 
                                                                    StartMessageID="MSG3" 
                                                                    EndMessageID="MSG3" />
                            </syncfusion:ActivationBoxCollection>
                        </syncfusion:UMLSequenceParticipant.ActivationBoxes>
                    </syncfusion:UMLSequenceParticipant>
                    
                    <!-- Database -->
                    <syncfusion:UMLSequenceParticipant ID="DB" Content="Database" IsActor="false">
                        <syncfusion:UMLSequenceParticipant.ActivationBoxes>
                            <syncfusion:ActivationBoxCollection>
                                <syncfusion:UMLSequenceActivationBox ID="ActDB1" 
                                                                    StartMessageID="MSG4" 
                                                                    EndMessageID="MSG5" />
                            </syncfusion:ActivationBoxCollection>
                        </syncfusion:UMLSequenceParticipant.ActivationBoxes>
                    </syncfusion:UMLSequenceParticipant>
                </syncfusion:ParticipantCollection>
            </syncfusion:UMLSequenceDiagramModel.Participants>
            
            <!-- Define messages -->
            <syncfusion:UMLSequenceDiagramModel.Messages>
                <syncfusion:MessageCollection>
                    <!-- Login request -->
                    <syncfusion:UMLSequenceMessage ID="MSG1" 
                                                  Content="Login(username, password)" 
                                                  FromParticipantID="User" 
                                                  ToParticipantID="Auth" 
                                                  Type="Synchronous" />
                    
                    <!-- Validate input (self message) -->
                    <syncfusion:UMLSequenceMessage ID="MSG3" 
                                                  Content="ValidateInput()" 
                                                  FromParticipantID="Auth" 
                                                  ToParticipantID="Auth" 
                                                  Type="Self" />
                    
                    <!-- Check credentials -->
                    <syncfusion:UMLSequenceMessage ID="MSG4" 
                                                  Content="CheckCredentials(username, password)" 
                                                  FromParticipantID="Auth" 
                                                  ToParticipantID="DB" 
                                                  Type="Synchronous" />
                    
                    <!-- Database response -->
                    <syncfusion:UMLSequenceMessage ID="MSG5" 
                                                  Content="Return result" 
                                                  FromParticipantID="DB" 
                                                  ToParticipantID="Auth" 
                                                  Type="Reply" />
                    
                    <!-- Login success -->
                    <syncfusion:UMLSequenceMessage ID="MSG6" 
                                                  Content="