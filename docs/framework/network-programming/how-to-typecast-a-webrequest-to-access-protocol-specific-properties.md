---
title: '방법: 프로토콜 관련 속성에 액세스하기 위해 WebRequest 형식 캐스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: 09bd551dad77358b1503871c6ee100a869adf75b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253429"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a>방법: 프로토콜 관련 속성에 액세스하기 위해 WebRequest 형식 캐스팅

이 예제에서는 프로토콜별 속성에 액세스할 수 있도록 WebRequest를 형식 캐스팅하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
  
```csharp  
HttpWebRequest httpreq =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a>참고 항목

- [플러그형 프로토콜 프로그래밍](programming-pluggable-protocols.md)
