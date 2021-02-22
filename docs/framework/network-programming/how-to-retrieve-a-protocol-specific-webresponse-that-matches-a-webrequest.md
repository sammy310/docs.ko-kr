---
title: '방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색'
description: .NET Framework에서 WebRequest와 일치하는 프로토콜별 WebResponse를 검색하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 920704bedce478ed5a4f7906379a634a3b2a4e31
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100584342"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a>방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색

이 예제에서는 WebRequest와 일치하는 프로토콜별 WebResponse를 검색하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
  
```csharp  
HttpWebRequest req = (HttpWebRequest)WebRequest.Create("http://www.contoso.com/");
HttpWebResponse resp = (HttpWebResponse)req.GetResponse();
```  
  
```vb  
Dim req As HttpWebRequest = CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)
Dim resp As HttpWebResponse = CType(req.GetResponse(), HttpWebResponse)
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  

 이 예제에는 다음 사항이 필요합니다.  
  
- **System.Net** 네임스페이스에 대한 참조.  
  
## <a name="see-also"></a>참조

- [데이터 요청](requesting-data.md)
