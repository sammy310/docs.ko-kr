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
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="57f60-103">방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색</span><span class="sxs-lookup"><span data-stu-id="57f60-103">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>

<span data-ttu-id="57f60-104">이 예제에서는 WebRequest와 일치하는 프로토콜별 WebResponse를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57f60-104">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57f60-105">예제</span><span class="sxs-lookup"><span data-stu-id="57f60-105">Example</span></span>  
  
```csharp  
HttpWebRequest req = (HttpWebRequest)WebRequest.Create("http://www.contoso.com/");
HttpWebResponse resp = (HttpWebResponse)req.GetResponse();
```  
  
```vb  
Dim req As HttpWebRequest = CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)
Dim resp As HttpWebResponse = CType(req.GetResponse(), HttpWebResponse)
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57f60-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="57f60-106">Compiling the Code</span></span>  

 <span data-ttu-id="57f60-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="57f60-107">This example requires:</span></span>  
  
- <span data-ttu-id="57f60-108">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="57f60-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f60-109">참조</span><span class="sxs-lookup"><span data-stu-id="57f60-109">See also</span></span>

- [<span data-ttu-id="57f60-110">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="57f60-110">Requesting Data</span></span>](requesting-data.md)
