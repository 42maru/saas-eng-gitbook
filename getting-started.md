---
description: Several steps required to use 42maru platform search service
---

# Getting Started

## Required

To use 42maru platform search service, you need to create an account and an application.

### Step 1 : Sign Up

If you want to sign up, click on \[Sign up for an account\] at the bottom of the 'Sign in' page.

![&apos;Sign in&apos; page](.gitbook/assets/image%20%2822%29.png)

![&apos;Sign up&apos; page](.gitbook/assets/image%20%2835%29.png)

### Step 2 : Create an Application

You can create a new application in the 'Create application' page after registration.

![Create application](.gitbook/assets/image%20%286%29.png)

* **Name** : Your application name.
* **Documents language** : Set a language for document searching. The application recognizes the selected language as the language of documents and questions input. Currently, we support 3 languages: Korean, English, and German. You can choose a language for each application. Document language can only be selected when the application is created and this setting cannot be altered after creating the application. if you need to change the language setting, you will need to create a new application.
* **Threshold** : The reference value which determines whether the results are exposed based on the similarity between the answer from searching and the correct answer. If the Threshold is too low, you will probably get answers to questions even if there is no answer. If the Threshold  is too high, you will get correct answers, but the number of the correct answers will be decreased.  Therefore, it is recommended to set the appropriate Threshold through trial and error.
* **Regions** : Set the location of the server. Select an area close to where the actual service will be provided. You can store data from an application on servers in multiple Regions. All API requests are routed to servers with fast response rates.

{% hint style="success" %}
Users can operate multiple applications in various settings and data at the same time. All features are separated by applications except the account management feature in 42maru platform. Applications are independent of each other, so change in one application does not affect the other.
{% endhint %}

#### Creating additional applications

If you want to add a new application, you can easily create one with the following steps:

1. Click on \[Current app\] on the top of the navigation bar
2. Switch to the 'Create application' page by clicking on the \[New Application\] in the drop-down menu.
3. Set all the given items on the 'Create application' page and click on \[Save\] to create the application.

![Initial page](.gitbook/assets/image%20%2860%29.png)

### Step 3 : Authentication

![Application information](.gitbook/assets/image%20%2833%29.png)

When you create an application, you can use most of the features in 42maru platform. Application Code value and API Key value of application are required to use the API and SDK.

**Checking Application Code value and API Key value**

These values can be found in the 'Settings' menu at the bottom of the left-hand navigation bar.

![API Key](.gitbook/assets/image%20%2866%29.png)

* **Application Information**: View, change, and delete application information.
* **Application Code**: When using the API, you can determine the key values to identify the application
* **API Key**:  You can check and change the key values of using/calling admin API, monitoring API and searching QA API.
* **IP Blacklist**: You can register, modify and delete IPs which should be blocked for all APIs.
* **Regions**: You can view and change the location of the server, which you want to store data for application.

## Next Steps

Once your account and application have been created, you can take full advantage of the 42maru platform features.

### Search Services

{% page-ref page="search-services/usd-mrc.md" %}

### Features

{% page-ref page="features/dashboard.md" %}

{% page-ref page="features/statistics/" %}

{% page-ref page="features/bulk-tests.md" %}

{% page-ref page="features/team.md" %}

{% page-ref page="features/settings.md" %}

### Additional Resources

{% page-ref page="additional-resources/glossary.md" %}

{% page-ref page="additional-resources/security.md" %}

{% page-ref page="additional-resources/usd-mrc.md" %}

{% page-ref page="additional-resources/troubleshooting.md" %}

