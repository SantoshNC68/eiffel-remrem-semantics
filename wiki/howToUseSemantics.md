<div id="main_content_wrap" class="outer">

<section id="main_content" class="inner">

## How to use semantics

To import the project user need to add to pom.xml

<div>

    <repositories>
       <repository>
           <id>jitpack.io</id>
           <url>https://jitpack.io</url>
       </repository>
    </repositories>
    <dependency>
        <groupId>com.github.Ericsson</groupId>
        <artifactId>eiffel-remrem-semantics</artifactId>
        <version>x.x.x</version>
    </dependency>

   </div>

Or import the project to pom.xml  

<div>

    repositories {
         ...
         maven { url 'https://jitpack.io' }
    }
    dependencies {
        compile("com.github.Ericsson:eiffel-remrem-semantics:x.x.x")
    }

   </div>

<div>
Eiffel REMReM Semantics contains implementation of Eiffel REMReM Protocol Interface. All methods of interface MsgService are implemented by SemanticsService class: generateMsg, getEventId, getEventType, getSupportedEventTypes, getEventTemplate, getServiceName, validateMsg, generateRoutingKey. Also in this class could be implemented more methods depending on the needs of developer.

The main task of Eiffel Semantics is to check a correctness of Eiffel message. Project contains JSON schemas for each Eiffel type of event. If you need to create new event type, you need to define the JSON schema for this event.

Each of Eiffel data types, for example links, gav, etc have its implementation in schema. If you need to extend event with some custom field, the JSON schema for this field and serializer should be created for it. Also event JSON schema need to be updated.

During the verification process input JSON for SemanticsService is updated with the protocol related fields, for example id.

All Eiffel events consist of 3 logical JSON objects: meta, data and links. The meta object contains meta-information describing the event: when it was created, where it came from, its type et cetera. The data object contains all fields specific to the event type – the payload of the event – including trace links to non-Eiffel entities. It is described in detail per event type. The links object is an array of trace links to other Eiffel events.

## Messages Table

Reference to Eiffel event templates can be found and downloaded from **[Templates](https://github.com/SantoshNC68/eiffel-remrem-generate/blob/master/wiki/semantics.html)**. 

Templates for Eiffel events to be used with [REMReM Generate](https://github.com/eiffel-community/eiffel-remrem-generate) are found below.  
Template can be downloaded and all fields labelled as required are to be mandatorily filled.  
The JSON file can be used with Eiffel REMReM Generate as described [here](https://eiffel-community.github.io/eiffel-remrem-generate/).

<font style="color: red;">Note¹: templates are avaialable from eiffel-remrem-semantics-0.2.5 version</font>


<font style="color: red;">Note²: templates are in full JSON syntax and filenames are in lowercase from eiffel-remrem-semantics-0.3.5 version</font>

</div>

<div>
<a href = "semantics.html">Choose Eiffel REMReM Semantics version:</a>
</div>
<div id="footer_wrap" class="outer">

<footer class="inner">

Eiffel REMReM Semantics maintained by [EiffelCommunity](https://github.com/eiffel-community)

</footer>

</div>