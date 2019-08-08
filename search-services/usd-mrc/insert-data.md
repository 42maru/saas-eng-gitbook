---
description: 'In order to use the MRC, you must insert your document.'
---

# Insert document

## Browser

You can add documents at the 'Documents' menu.

![&apos;Document&apos; page](../../.gitbook/assets/image%20%284%29.png)

Click on the \[File upload\] button, and a new window which you can upload files by drag and drop will pop up.

{% hint style="info" %}
Supports formatted files: json, excel
{% endhint %}

![Insert document](../../.gitbook/assets/image%20%287%29.png)

{% api-method method="post" host="http://alpha.42maru.com" path="/api/application/documents" %}
{% api-method-summary %}
Insert a document
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

{% endapi-method-response-example-description %}

```text

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
    "data": {}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

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

