---

제목: 사용자 기반 푸시 알림 사용

키워드: 사용자 기반 푸시 알림, userId
copyright:
 years: 2015, 2016

---

# 사용자 기반 알림 사용
{: #user_based_notifications}
마지막 업데이트 날짜: 2016년 8월 16일
{: .last-updated}

사용자 ID 기반 {{site.data.keyword.mobilepushshort}}은 사용자 정의된 메시지를 사용하는 모바일 앱 사용자가 대상입니다. 사용자 기반 알림은 특정 개인이 개인 환경 설정과 선택사항을 이용할 수 있도록 도울 수 있습니다.   

## 사용자 ID를 사용하여 디바이스 등록
사용자 ID로 대상이 지정되는 푸시 알림을 사용하려면 사용자 ID를 사용하여 디바이스를 등록하고 {{site.data.keyword.mobilepushshort}} 서비스가 프로비저닝될 때 할당되는 'clientSecret'을 전달해야 합니다. 올바른 'clientSecret'이 없으면 디바이스 등록에 실패합니다.   

애플리케이션에서 디바이스 등록 API에 제공하는 모든 문자열이 사용자 ID가 될 수 있습니다. 일반적으로 모바일 애플리케이션은 제일 먼저 인증 주기를 실행하며 여기서 모바일 앱 사용자가 인증 서비스(예: [{{site.data.keyword.amafull}}](https://console.ng.bluemix.net/docs/services/mobileaccess/index.html))에 대해 인증됩니다. 인증에 성공하면 인증된 사용자 ID가 'clientSecret'과 함께 푸시 디바이스 등록 API에 전달됩니다. 'clientSecret'이 있으면 사용자 ID와 모바일 디바이스 등록의 인증된 연관만 적용됩니다. 

'clientSecret'을 기밀로 유지하고 모바일 앱으로 하드코딩하지 마십시오. 애플리케이션 런타임 중에 동적으로 'clientSecret'에 가져오는 데 사용할 수 있는 여러 애플리케이션 초기화 패턴이 있습니다. 시퀀스 다이어그램에서 이 패턴을 간략히 보여줍니다. 

![Enable_Push](images/init_client_secret.jpg) 

'익명' 사용자와 연관되도록 디바이스를 등록할 수도 있습니다. 이를 수행하려면 사용자 ID와 'clientSecret' 인수가 필요 없는 디바이스 등록 API의 변형을 사용해야 합니다.    

## 사용자 로그인/로그아웃 동기화 및 푸시 알림 사용 

사용자가 로그인한 경우에만 알림을 보내도록 선택할 수 있습니다.  

예를 들어, 가족 또는 직장의 팀이 디바이스를 공유하는 경우 가족 또는 팀의 특정 사용자를 지정해야 합니다. 이와 같은 유스 케이스에서는 현재 애플리케이션 사용자의 ID를 추적하도록 애플리케이션을 보호하는 사용자 로그인/로그아웃 시퀀스가 있습니다. 특정 사용자가 대상인 알림을 항상 해당 사용자만 수신하도록 하려면 로그인한 후 로그인한 사용자의 사용자 ID를 전달하여 디바이스 등록 API를 호출하십시오. 마찬가지로 로그아웃하기 전에 디바이스 등록 해제 API를 호출하십시오. 로그인, 로그아웃과 함께 이러한 푸시 API의 시퀀스를 지정하면 특정 사용자를 대상으로 작성된 푸시 알림이 해당 사용자에게만 전송됩니다. 