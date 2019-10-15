---
description: >-
  You can upload, modify and inquire the target data for searching in the
  'Documents' menu. To use MRC, you must upload your documents.
---

# Documents

![&apos;Document&apos; page](../.gitbook/assets/doc_upload_4.PNG)

*  **ID:** A unique code assigned to each document. If you do not specify a code, the system will automatically assign a code.
*  **Title** \(Required\): ****A title of a document.
*  **Content** \(Required\): Core target data for searching. Searching with MRC is more suitable for longer paragraphs than shorter ones.
* **Created at:** Shows the time the documents uploaded on the server.

### Insert documents by 'File upload' button

Click the \[File upload\] button, and a new drag and drop window for upload will pop up. The same can be done by clicking the 'File upload' button in the '…' icon button at the top right of the page.

![&apos;Document default\(File upload\)&apos; page](../.gitbook/assets/doc_1.PNG)

{% hint style="info" %}
Supported file formats: json, xlsx
{% endhint %}

![&apos;Upload document&apos; page](../.gitbook/assets/image%20%285%29.png)

Drop a file or click the box to upload. For xlsx files, it is recommended that the files contain fields for ID, Title and Content. Click the 'Preview' button to preview the data.

{% hint style="warning" %}
* Title and Content are mandatory, and ID is optional.
* Only the first sheet of the xlsx file can be called up.
* Blanked columns are not imported.
{% endhint %}

![&apos;Document upload file preview&apos; page](../.gitbook/assets/doc_upload_2.PNG)

![&apos;Document upload file preview\_configure the ID, Title, C&apos; page](../.gitbook/assets/doc_upload_3_2.PNG)

To configure ID, Title and Contents fields of documents, click the drop-down box at the top of the first row of the table. Then, click the 'Save' button at the bottom of the page to upload the file to the server.

### **Insert a single document by 'Add document' button**

![&apos;Add a document&apos; button](../.gitbook/assets/image%20%2818%29.png)

![](../.gitbook/assets/doc_upload_5.PNG)

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



