---
title: '방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: fee2b725afbceef45b9651a7cd88a61b37952e32
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087380"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="5ef77-102">방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색</span><span class="sxs-lookup"><span data-stu-id="5ef77-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="5ef77-103">이 예제에서는 WebRequest와 일치하는 프로토콜별 WebResponse를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ef77-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ef77-104">예제</span><span class="sxs-lookup"><span data-stu-id="5ef77-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5ef77-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5ef77-105">Compiling the Code</span></span>  
 <span data-ttu-id="5ef77-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef77-106">This example requires:</span></span>  
  
-   <span data-ttu-id="5ef77-107">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="5ef77-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef77-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ef77-108">See also</span></span>

- [<span data-ttu-id="5ef77-109">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="5ef77-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
