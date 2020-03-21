---
title: <generatePublisherEvidence> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154116"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence> 요소
런타임이 CAS(코드 <xref:System.Security.Policy.Publisher> 액세스 보안)에 대한 증명 을 만드는지 여부를 지정합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<생성게시자>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에서 증명 증명 <xref:System.Security.Policy.Publisher> 을 만드는지 여부를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|Description|  
|-----------|-----------------|  
|`false`|증거를 만들지 <xref:System.Security.Policy.Publisher> 않습니다.|  
|`true`|증거를 <xref:System.Security.Policy.Publisher> 만듭니다. 이것이 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> .NET Framework 4 이상에서는 이 요소가 어셈블리 로드 시간에 영향을 주지 않습니다. 자세한 내용은 [보안 변경의](../../../security/security-changes.md)"보안 정책 단순화" 섹션을 참조하십시오.  
  
 공통 언어 런타임(CLR)은 로드 시 Authenticode 서명을 <xref:System.Security.Policy.Publisher> 확인하여 어셈블리에 대한 증거를 만들려고 합니다. 그러나 기본적으로 대부분의 응용 프로그램에는 <xref:System.Security.Policy.Publisher> 증거가 필요하지 않습니다. 표준 CAS 정책은 <xref:System.Security.Policy.PublisherMembershipCondition>에 의존하지 않습니다. 응용 프로그램이 사용자 지정 CAS 정책을 사용하여 컴퓨터에서 실행되거나 부분 신뢰 환경에서 요구 사항을 <xref:System.Security.Permissions.PublisherIdentityPermission> 충족하려는 경우가 아니면 게시자 서명 확인과 관련된 불필요한 시작 비용을 피해야 합니다. ID 권한에 대한 요구는 항상 완전 신뢰 환경에서 성공합니다.  
  
> [!NOTE]
> 서비스는 `<generatePublisherEvidence>` 시작 성능을 향상시키기 위해 요소를 사용하는 것이 좋습니다.  이 요소를 사용하면 시간 시간 및 서비스 시작 취소를 유발할 수 있는 지연을 방지할 수도 있습니다.  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일에서만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `<generatePublisherEvidence>` 요소를 사용하여 응용 프로그램에 대한 CAS 게시자 정책 검사를 사용하지 않도록 설정하는 방법을 보여 주습니다.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
