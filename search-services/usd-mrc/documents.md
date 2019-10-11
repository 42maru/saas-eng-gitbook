---
description: >-
  You can upload, modify, and inquiry the data that is a target to the search at
  the 'Documents' menu. In order to use the MRC, you must insert your document.
---

# Documents

### Insert documents by 'File upload' button

![&apos;Document&apos; page](../../.gitbook/assets/image%20%287%29.png)

Click on the \[File upload\] button, and a new window which you can upload files by drag and drop will pop up. The same can be done by clicking on the 'File upload' button in the  '…' icon button at the top right of the page.

{% hint style="info" %}
Supports formatted files: json, excel
{% endhint %}

![&apos;Upload document&apos; page](../../.gitbook/assets/image%20%285%29.png)

Drop a file or click the area to upload. For Excels, it is recommended that they consist of fields for ID, Title, and Content.Click the 'Preview' button to preview the data**.**

{% hint style="warning" %}
* At least two columns are required for the Title and Content because the ID is not essential.
* Only the first sheet of the excel file can be called up.
* Columns blanked are not imported.
{% endhint %}

![&apos;Uploaded documents preview&apos; page](../../.gitbook/assets/image%20%2821%29.png)

![&apos;Uploaded documents preview\_field defined&apos; page](../../.gitbook/assets/image%20%2852%29.png)

Click the drop-down box at the top of the first row of the table to define the field to be the ID, Title, and Contents to configure the documents. Then click the 'Save' button at the bottom of the page to upload the file to the server.

### **Insert a single document by 'Add document' button**

![Add document button](../../.gitbook/assets/image%20%2830%29.png)

![&apos;Add a single document&apos; modal](../../.gitbook/assets/image%20%2845%29.png)

{% api-method method="post" host="http://alpha.42maru.com" path="/api/application/documents" %}
{% api-method-summary %}
Insert documents by API
{% endapi-method-summary %}

{% api-method-description %}
Insert a document
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-PLATFORM42-APP-ID" type="string" required=true %}
Application id
{% endapi-method-parameter %}

{% api-method-parameter name="X-PLATFORM42-API-KEY" type="string" required=true %}
Key with access to application
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "data": {
        "id": 3044702,
        "doc_id": 337842,
        "application_id": 24,
        "title": "limiting enzyme",
        "content": "By reacting with the target DNA using several types of restriction enzymes, each of which recognizes a particular sequence of bases and cuts the DNA, indicating where the specific restriction enzyme action is relatively located. Using this, we draw up a genetic map..",
        "deleted": false,
        "created_at": "2019-08-07T02:27:54",
        "updated_at": null
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Content is an essential information.
{% endapi-method-response-example-description %}

```yaml
{
    "error_message": "Required is content"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Body parameters

{% hint style="info" %}
content is an essential information.
{% endhint %}

```yaml
{
    "doc_id": 337842,
    "title": "limiting enzyme",
    "content": "By reacting with the target DNA using several types of restriction enzymes, each of which recognizes a particular sequence of bases and cuts the DNA, indicating where the specific restriction enzyme action is relatively located. Using this, we draw up a genetic map."
}
```

{% api-method method="post" host="http://alpha.42maru.com" path="/api/application/documents/bulk" %}
{% api-method-summary %}
Insert multiple documents
{% endapi-method-summary %}

{% api-method-description %}
Insert multiple documents
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-PLATFORM42-APP-ID" type="string" required=true %}
Application id
{% endapi-method-parameter %}

{% api-method-parameter name="X-PLATFORM42-API-KEY" type="string" required=true %}
Key with access to application
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "data": {
        "message": "success"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Content is an essential information.
{% endapi-method-response-example-description %}

```yaml
{
    "error_message": "Required is content"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=413 %}
{% api-method-response-example-description %}
Inserted file is too big
{% endapi-method-response-example-description %}

```yaml
{
    "error_message": "Too big content_length must be shorter than 10000000"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Body Parameters

{% hint style="info" %}
content is an essential information.
{% endhint %}

```yaml
[
    {
        "doc_id": 337842,
        "title": "limiting enzyme",
        "content": "By reacting with the target DNA using several types of restriction enzymes, each of which recognizes a particular sequence of bases and cuts the DNA, indicating where the specific restriction enzyme action is relatively located. Using this, we draw up a genetic map."
    },
    {
        "doc_id": 337842,
        "title": "limiting enzyme",
        "content": "The part of a person's DNA that produces useful substances is cut with a restriction enzyme and then connected the piece to the plasmid DNA of E. coli. Insert modified plasmid into E. coli, producing a large quantity of useful material in a short time."
    },
    {
        "doc_id": 1758246,
        "title": "Actor B",
        "content": "Yale University \r\n"
    },
    {
        "doc_id": 1758246,
        "title": "Actor B",
        "content": "--《 Movie-1 》 (Year 2017) – Casting of A\r\n--《 Movie-2》 (Year 2016) – Casting of B\r\n--《 Movie-3 》 (Year 2016) - Casting of C \r\n"
    }
]
```

## Documents management



