---
title: <generatePublisherEvidence> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: b04ef53d6e9c3d954b0925ea8634b3d220b36af7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116579"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence > 요소
런타임이 CAS (코드 액세스 보안)에 대 한 <xref:System.Security.Policy.Publisher> 증명 정보를 만들지 여부를 지정 합니다.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**  
  
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
|`enabled`|필수 특성입니다.<br /><br /> 런타임이 <xref:System.Security.Policy.Publisher> 증명 정보를 만들지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Policy.Publisher> 증명 정보를 만들지 않습니다.|  
|`true`|<xref:System.Security.Policy.Publisher> 증명 정보를 만듭니다. 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> .NET Framework 4 이상에서이 요소는 어셈블리 로드 시간에 영향을 주지 않습니다. 자세한 내용은 [보안 변경 내용](../../../security/security-changes.md)의 "보안 정책 단순화" 섹션을 참조 하세요.  
  
 CLR (공용 언어 런타임)은 로드할 때 Authenticode 서명을 확인 하 여 어셈블리에 대 한 <xref:System.Security.Policy.Publisher> 증명 정보를 만듭니다. 그러나 기본적으로 대부분의 응용 프로그램에는 <xref:System.Security.Policy.Publisher> 증명 정보가 필요 하지 않습니다. 표준 CAS 정책은 <xref:System.Security.Policy.PublisherMembershipCondition>를 사용 하지 않습니다. 응용 프로그램이 사용자 지정 CAS 정책을 사용 하는 컴퓨터에서 실행 되지 않거나 부분 신뢰 환경에서 <xref:System.Security.Permissions.PublisherIdentityPermission>에 대 한 요구를 충족 하는 경우에만 게시자 서명을 확인 하는 데 관련 된 불필요 한 시작 비용을 피해 야 합니다. (Id 권한 요구는 항상 완전 신뢰 환경에서 성공 합니다.)  
  
> [!NOTE]
> 서비스에서 `<generatePublisherEvidence>` 요소를 사용 하 여 시작 성능을 향상 시키는 것이 좋습니다.  이 요소를 사용 하면 시간 초과 및 서비스 시작 취소가 발생할 수 있는 지연을 방지할 수도 있습니다.  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `<generatePublisherEvidence>` 요소를 사용 하 여 응용 프로그램에 대 한 CAS 게시자 정책 검사를 사용 하지 않도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
