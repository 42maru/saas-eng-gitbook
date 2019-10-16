---
description: >-
  The MRC search engine uses the uploaded documents to find answers (to
  questions).
---

# Simulation

## Browser

Navigate the 'Simulation' menu. Then enter your questions into the text box.

![&apos;Simulation&apos; page](../.gitbook/assets/image%20%2857%29.png)

If you have entered the questions correctly, you can check the answers and the retrieved documents. The correct answer is sorted in descending order by the confidence value.

![&apos;Simulation&apos; page](../.gitbook/assets/image%20%2812%29.png)

{% api-method method="get" host="http://alpha.42maru.com" path="/api/broker/answer" %}
{% api-method-summary %}
Get MRC result
{% endapi-method-summary %}

{% api-method-description %}
Return the correct answer to the question.
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

{% api-method-body-parameters %}
{% api-method-parameter name="query" type="string" required=true %}
Questions to be forwarded to the MRC search engine.
{% endapi-method-parameter %}

{% api-method-parameter name="debug" type="boolean" required=false %}
When set to true, you can check the search results in more detail.
{% endapi-method-parameter %}

{% api-method-parameter name="count" type="integer" required=false %}
Number of correct answers to receive in response.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Debug is true
{% endapi-method-response-example-description %}

```yaml
{
    "data": {
        "answer": [
            "Answer candidate 1",
            "Answer candidate 2",
            "Answer candidate 3"
        ],
        "query": "Who is owner of Lexus?",
        "threshold": 0.01,
        "req_time": "2019-08-08T15:30:00",
        "passage_response_time": "2019-08-08T15:30:00",
        "mrc_response_time": "2019-08-08T15:30:00",
        "entries": []
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Query key is essential
{% endapi-method-response-example-description %}

```yaml
{
    "error_message": "Required is query"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Wrong API key
{% endapi-method-response-example-description %}

```yaml
{
    "timestamp": "2019-08-08T15:30:17.060+0000",
    "status": 403,
    "error": "Forbidden",
    "message": "Access Denied",
    "path": "/api/broker/answer"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

