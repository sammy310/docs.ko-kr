---
description: '자세히 알아보기: CustomBindingElement'
title: CustomBindingElement
ms.date: 03/30/2017
ms.assetid: df959dc5-1aef-4338-a123-6ff3e7bc37af
ms.openlocfilehash: fc3f1fcbfc54ff082f87e04a894226ff9ca996bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757516"
---
# <a name="custombindingelement"></a>CustomBindingElement

CustomBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class CustomBindingElement : BindingElement  
{  
  string Name;  
};  
```  
  
## <a name="methods"></a>메서드  

 CustomBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 CustomBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="name"></a>Name  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 바인딩의 구성 이름을 포함하는 문자열입니다. 이 값은 사용자 지정 바인딩의 식별 문자열 역할을 하는 사용자 정의 문자열입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Channels.CustomBinding>
