---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: e67cc316b8747ee785055ceb4f954988fa82a44c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940622"
---
# <a name="usemanagedpresentation"></a>\<useManagedPresentation>
WS-Trust의 CardSpace 프로필을 지원하는 CardSpace 보안 토큰 서비스와 통신하는 데 사용되는 바인딩 요소입니다. 이 요소는 특성이 없고 빈 스위치로 존재합니다.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<useManagedPresentation>  
  
## <a name="syntax"></a>구문  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding>](../../../misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## <a name="remarks"></a>설명  
 이 요소는 ID 공급자가 정책에서 WS-Trust의 CardSpace 프로필을 지원함을 나타내는 데 사용됩니다. 그러한 정책 어설션을 게시하는 ID 공급자는 해당 CardSpace 프로필을 기반으로 토큰을 발급할 수 있어야 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [바인딩](../../../wcf/bindings.md)
- [바인딩 확장](../../../wcf/extending/extending-bindings.md)
- [사용자 지정 바인딩](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
