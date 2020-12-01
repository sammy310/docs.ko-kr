---
title: '방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색'
description: .NET Framework에서 WebRequest와 일치하는 프로토콜별 WebResponse를 검색하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: fd163c115dcd19c05f93f4c202b043440834ba9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266742"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="6915b-103">방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색</span><span class="sxs-lookup"><span data-stu-id="6915b-103">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>

<span data-ttu-id="6915b-104">이 예제에서는 WebRequest와 일치하는 프로토콜별 WebResponse를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6915b-104">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6915b-105">예제</span><span class="sxs-lookup"><span data-stu-id="6915b-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6915b-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6915b-106">Compiling the Code</span></span>  

 <span data-ttu-id="6915b-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6915b-107">This example requires:</span></span>  
  
- <span data-ttu-id="6915b-108">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="6915b-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6915b-109">참조</span><span class="sxs-lookup"><span data-stu-id="6915b-109">See also</span></span>

- [<span data-ttu-id="6915b-110">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="6915b-110">Requesting Data</span></span>](requesting-data.md)
