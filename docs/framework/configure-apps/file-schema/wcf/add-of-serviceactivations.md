---
title: <serviceActivations>의 <add>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850323"
---
# <a name="add-of-serviceactivations"></a>\<serviceActivations>의 \<add>

WCF (Windows Communication Foundation) 서비스 형식에 매핑되는 가상 서비스 활성화 설정을 정의할 수 있는 구성 요소입니다. .svc 파일 없이도 WAS/IIS에서 호스트되는 서비스를 활성화할 수 있습니다.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a>구문

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|attribute|Description|
|---------------|-----------------|
|공장|서비스 활성화 요소를 생성하는 팩터리의 CLR 형식 이름을 지정하는 문자열입니다.|
|서비스|서비스를 구현하는 ServiceType입니다(App_Code 폴더에 있는 경우 정규화된 Typename 또는 짧은 Typename).|
|relativeAddress|현재 IIS 애플리케이션 내에서의 상대 주소입니다(예: &quot;Service.svc&quot;). WCF 4.0에서이 상대 주소는 알려진 파일 확장명 (.svc,. .xamlx, ...) 중 하나를 포함 해야 합니다. RelativeUrl에 대 한 물리적 파일이 존재 하지 않습니다.|

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|Description|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|활성화 설정을 설명하는 구성 섹션입니다.|

## <a name="remarks"></a>설명

다음 예제에서는 web.config 파일 내에서 활성화 설정을 구성하는 방법을 보여 줍니다.

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

이 구성을 사용하여 .svc 파일을 사용하지 않고도 GreetingService를 활성화할 수 있습니다.

`<serviceHostingEnvironment>`는 애플리케이션 수준 구성입니다. 구성을 포함하는 `web.config`를 가상 애플리케이션의 루트 아래에 배치해야 합니다. 또한 `serviceHostingEnvironment` 는 machineToApplication 된 상속 가능 섹션입니다. 컴퓨터의 루트에 단일 서비스를 등록하는 경우 애플리케이션의 모든 서비스가 이 서비스를 상속합니다.

구성 기반 활성화는 http 및 http가 아닌 프로토콜을 통한 활성화를 모두 지원합니다. 이 클래스에는 relativeAddress,. .svc 또는. .xamlx의 확장이 필요 합니다. 직접 작성한 확장을 알려진 buildProviders에 매핑할 수 있으며, 이렇게 하면 모든 확장에서 서비스를 활성화할 수 있습니다. 충돌이 발생하면 `<serviceActivations>` 섹션이 .svc 등록을 재정의합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
