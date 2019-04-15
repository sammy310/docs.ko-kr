---
title: PeerCustomResolverBindingElement
ms.date: 03/30/2017
ms.assetid: 9ccc2770-a20e-4dff-9970-f56ad8aec2b5
ms.openlocfilehash: 47a4d7a9e0c2b0f8a6fc3beb964bf4dd649f7c0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220762"
---
# <a name="peercustomresolverbindingelement"></a>PeerCustomResolverBindingElement
PeerCustomResolverBindingElement  
  
## <a name="syntax"></a>구문  
```csharp
class PeerCustomResolverBindingElement : PeerResolverBindingElement
{  
    string Address;
    string Binding;
};
```  
  
## <a name="methods"></a>메서드  
 PeerCustomResolverBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 PeerCustomResolverBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="address"></a>주소  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 피어 사용자 지정 확인자의 주소입니다.  
  
### <a name="binding"></a>바인딩  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 바인딩의 구성 이름입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement>
