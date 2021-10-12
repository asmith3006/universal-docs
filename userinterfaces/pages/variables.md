---
description: Variables available in PowerShell Universal pages.
---

# Variables

{% hint style="info" %}
This feature requires a [PowerShell Universal license](../../licensing.md). 
{% endhint %}

Variables allow you modify the functionality of a page depending on factors such as the user name or URL route. Variable-based routes allow you to create dynamic pages based on the URL the user is visiting. 

Variables that are defined with Platform \ Variables will also be available to pages.

## Viewing Variables

Variables can be viewed when editing a page. To view variables, click Edit and then Variables. 

![](<../../.gitbook/assets/image (298).png>)

A drawer will appear with the variables for the current page. 

![](<../../.gitbook/assets/image (301) (1).png>)

## Using Variables

Variables can be used anywhere you can type a property value. For example, if you have an Alert, you could use the `$pagename` variable within the title property. 

![](<../../.gitbook/assets/image (293).png>)

When the page is rendered, the variable will be replaced. 

![](<../../.gitbook/assets/image (299).png>)



You can also use variables within targets and data sources. This allows you to call URLs that will change based on the variable. 

![](<../../.gitbook/assets/image (297).png>)

You can also use variables to provide hidden input fields to APIs and scripts. 

 

![](<../../.gitbook/assets/image (296) (1).png>)

## Page Variables

You can load additional data when the page is loading by providing a data source to in the page properties. The data source should return a single PSCustomObject or hashtable. The properties of the object will become variables within the page. 

For example, assume you have an API that returns the following hashtable. 

```
@{
    Name = "My Name"
    Title = "My Title"
}
```

Selecting this API as the data source for the page would then create the variables `$Name` and `$Title` within the page. 

You can also use Route Variables within the data source to customize which API is called based on the route visited. 

## Route Variables

Route variables need to be defined when creating the URL for the page. Each section of the URL that starts with `:` will be treated as a variable. 

For example, this page defines a single route variable. 

![](<../../.gitbook/assets/image (294).png>)

Within the page, the route variables will appear within the variable drawer. 

![](<../../.gitbook/assets/image (300) (1).png>)
