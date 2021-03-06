---

copyright:
 years: 2015, 2017

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Chrome 앱 및 확장기능에 기본 알림 전송 
{: #web_extensions_notifications}
마지막 업데이트 날짜: 2017년 1월 11일
{: .last-updated}

애플리케이션을 개발한 후에는 푸시 알림을 전송할 수 있습니다.  

1. **알림 전송**을 선택하고 **받는 사람** 옵션으로 **웹 알림**을 선택하여 메시지를 작성하십시오.  
2. **메시지** 필드에 전달할 메시지를 입력하십시오.
3. 다음과 같은 선택적 설정을 제공하도록 선택할 수 있습니다.
  - **알림 제목**: 메시지 경보 표제로 표시할 텍스트입니다.
  - **알림 아이콘 URL**: 메시지를 앱 알림 아이콘과 함께 전달해야 하는 경우 필드에서 아이콘에 대한 링크를 제공하십시오.
  - **접기 키**: 접기 키는 알림에 첨부됩니다. 디바이스가 오프라인 상태일 때 접기 키가 동일한 여러 개의 알림이 순차적으로 도착하는 경우 해당 알림은 접혀 있습니다. 디바이스가 온라인 상태가 되면 FCM/GCM 서버에서 알림을 수신하고 동일한 접기 키가 있는 최신 알림만 표시합니다. 접기 키가 설정되어 있지 않는 경우에는 나중에 전달할 수 있도록 새 메시지와 이전 메시지가 모두 저장됩니다.
  - **유효 기간**: 이 값은 초 단위로 설정됩니다. 이 매개변수를 지정하지 않는 경우 FCM/GCM 서버는 메시지를 4주 동안 저장하고 전달하려고 합니다. 4주 후에 유효성이 만료됩니다. 가능한 값 범위는 0 - 2,419,200초입니다.
  - **유휴 시 지연**: 이 값을 `true`로 설정하면 디바이스가 유휴 상태인 경우 FCM/GCM 서버가 알림을 전달하지 않습니다. 디바이스가 유휴 상태인 경우에도 알림이 전달되도록 하려면 이 값을 `false`로 설정하십시오.
  - **추가 페이로드**: 알림에 대한 사용자 정의 페이로드 값을 지정합니다.

다음 이미지는 대시보드의 Chrome 앱 및 확장기능 알림 옵션을 표시합니다.

  ![알림 화면](images/push_chrome_extns.jpg)
  
## 다음 단계
  {: #next_steps_tags}

정상적으로 기본 알림을 설정한 후에는 태그 기반 알림 및 고급 옵션을 구성할 수 있습니다. 

이러한 {{site.data.keyword.mobilepushshort}} 서비스 기능을 앱에 추가하십시오. 태그 기반 알림을 사용하려면 [태그 기반 알림](c_tag_basednotifications.html)을 참조하십시오. 고급 알림 옵션을 사용하려면 [고급 알림](t_advance_badge_sound_payload.html)을 참조하십시오. 
