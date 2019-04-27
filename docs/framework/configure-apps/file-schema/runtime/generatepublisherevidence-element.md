---
title: <generatePublisherEvidence> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09a12f062b2fe3ad6e5ac90f0d268bbbeab44876
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674144"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence > 요소
런타임을 만드는 지 여부를 지정 <xref:System.Security.Policy.Publisher> 코드 액세스 보안 (CA)에 대 한 증거입니다.  
  
 \<configuration>  
\<runtime>  
\<generatePublisherEvidence>  
  
## <a name="syntax"></a>구문  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임을 만드는 지 여부를 지정 <xref:System.Security.Policy.Publisher> 증명 정보입니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|만들어지지는지 않습니다 <xref:System.Security.Policy.Publisher> 증명 정보입니다.|  
|`true`|만듭니다 <xref:System.Security.Policy.Publisher> 증명 정보입니다. 이 값이 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  에 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 및 나중에이 요소에 어셈블리 로드 시간에 영향을 주지 않습니다. 자세한 내용은의 "보안 정책 단순화" 섹션을 참조 하세요 [보안 변경 내용](../../../../../docs/framework/security/security-changes.md)합니다.  
  
 만들려는 로드 시 Authenticode 서명을 확인 하려고 하는 CLR (공용 언어 런타임) <xref:System.Security.Policy.Publisher> 어셈블리 증명 정보입니다. 그러나 기본적으로 대부분의 응용 프로그램 않아도 <xref:System.Security.Policy.Publisher> 증명 정보입니다. 표준 CAS 정책을 사용 하지는 <xref:System.Security.Policy.PublisherMembershipCondition>합니다. 관련 응용 프로그램 사용자 지정 CAS 정책 사용 하 여 컴퓨터에서 실행 하거나에 대 한 요구를 충족 하려는 경우가 아니면 게시자 서명 확인 된 불필요 한 시작 비용은 안 <xref:System.Security.Permissions.PublisherIdentityPermission> 부분 신뢰 환경에서. (Id 권한 요청이 항상 완전 신뢰 환경에서 성공 합니다.)  
  
> [!NOTE]
>  사용 하 여 서비스 하는 것이 좋습니다는 `<generatePublisherEvidence>` 시작 성능을 개선 하는 요소입니다.  이 요소를 사용 하는 시간 제한 및 서비스의 시작을 취소 될 수 있는 지연을 방지할 수 있습니다.  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법의 `<generatePublisherEvidence>` 요소를 응용 프로그램에 대 한 게시자 정책 CA에 대 한 확인을 사용 하지 않도록 설정 합니다.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
