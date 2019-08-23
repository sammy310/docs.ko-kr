---
title: <clear>of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: e7e3bebd85decbaa4d216743f9bea9e135b87995
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926129"
---
# <a name="clear-of-claimtyperequirements-element"></a>\<\<claimTypeRequirements > 요소의 > 지우기
페더레이션 자격 증명에서 제거할 모든 클레임의 형식을 지정합니다. 이를 통해 컬렉션이 빈 상태로 시작됩니다.  
  
 \<system.ServiceModel>  
\<bindings>  
\<wsFederatedBinding>  
\<binding>  
\<security>  
\<message>  
\<claimTypeRequirements>  
  
## <a name="syntax"></a>구문  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|필요한 클레임 형식의 컬렉션을 지정합니다. 각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.<br /><br /> 페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다. 예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다. 이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
