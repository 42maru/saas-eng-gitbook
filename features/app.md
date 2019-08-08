---
description: >-
  ${Platform} 의 계정관리를 제외한 모든 기능들은 ${APP} 단위로 구분되어 있기 때문에 ${APP} 은 서로 정보를 공유하거나
  영향을 주지 않습니다.
---

# Application

## Setting

Setting 탭에서 ${app} 대한 정보를 확인하고 설정값들을 변경 수 있습니다.

### APP

* Application Code : ${APP} 생성시 자동으로 생성되는 고유한 ID 입니다.
* API Key : ${APP} 생성시 자동으로 생성되는 비밀 Key 입니다. ${platform} 웹 인터페이스 이외의 수단\(SDK,API\)으로 ${App} 의 정보를 조회 및 수정할 때 사용됩니다. 

### ${MRC}

* 애플리케이션 이름 : ${APP} 이름
* 임계값 : 임계값은 검색엔진 성능의 엄격함을 나타냅니다. 검색엔진이 ${query} 를 전달받으면 우선 ${answer}이 될만한 후보군들을 찾아냅니다. 그리고 각 후보가 ${answer}에 적절한지 점수를 매깁니다. 최종적으로 검색엔진은 임계값 이상의 점수를 가진 후보군 중 가장 높은 점수의 후보군을  ${answer}로 사용자에게 전달합니다. 만약 모든 후보군이 임계값에 미치지 못한다면 검색엔진은 ${noanswer} 로 판단합니다.

{% hint style="info" %}
${App} 의 설정은 최초 ${App} 생성시에만 가능합니다.
{% endhint %}

![http://alpha.42maru.com/applications/{app\_code}/settings](../.gitbook/assets/image-9.png)

