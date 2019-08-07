---
description: '${MRC} 검색엔진은 업로드된 ${passage} 데이터를 바탕으로 ${query} 의 ${answer} 를 찾아냅니다.'
---

# Querying

## Browser

Simulation 탭으로 이동합니다. 그리고 텍스트 박스\(Questions\) 안에 ${query} 를 입력합니다.

![http://alpha.42maru.com/applications/{app\_code}/mrc/simulation](../../.gitbook/assets/image-6.png)

정상적으로 ${query} 입력하셨다면 ${answer} 와 해당 ${answer} 를 찾아낸 ${passage} 를 확인하실 수 있습니다. ${answer} 는 ${validity} 따라 정렬되어 가장 높은 ${validity}를 가진 ${answer} 를 화면 상단에 노출시킵니다.

> 정답과 함께 나타난 값\(0.996\) 은 해당 ${answer} 에 대한 검색엔진의 신뢰도를 의미합니다.

![](../../.gitbook/assets/image-7.png)

## SDK

{% api-method method="get" host="${API-SERVER}" path="/api/broker/answer" %}
{% api-method-summary %}
API
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-PLATFORM42-APP-ID" type="string" required=true %}
${app의 id 
{% endapi-method-parameter %}

{% api-method-parameter name="X-PLATFORM42-API-KEY" type="string" required=true %}
${app} 의 접근권한을 가진 Key
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="query" type="string" required=true %}
${MRC}검색 엔진에 전달할 ${query}
{% endapi-method-parameter %}

{% api-method-parameter name="debug" type="boolean" required=false %}
true로 설정시 검색 결과를 자세히 확인할 수 있다. 
{% endapi-method-parameter %}

{% api-method-parameter name="count" type="integer" required=false %}
검색엔진이 찾아낸 ${answer} 후보 중 상위 몇 개의 ${answer} 를 받을 것인지에 대한 설정
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```yaml
{
    "data": {
        "answer": [
            "절충장군전라좌도수군절도사",
            "위인",
            "장군"
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

