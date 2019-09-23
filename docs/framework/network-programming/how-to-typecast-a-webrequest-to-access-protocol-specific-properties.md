---
title: '방법: 프로토콜 관련 속성에 액세스하기 위해 WebRequest 형식 캐스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: a224d9dbab0157d77c05a5937fe35c027296a674
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048020"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="9d8f2-102">방법: 프로토콜 관련 속성에 액세스하기 위해 WebRequest 형식 캐스팅</span><span class="sxs-lookup"><span data-stu-id="9d8f2-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="9d8f2-103">이 예제에서는 프로토콜별 속성에 액세스할 수 있도록 WebRequest를 형식 캐스팅하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d8f2-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d8f2-104">예</span><span class="sxs-lookup"><span data-stu-id="9d8f2-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d8f2-105">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d8f2-105">See also</span></span>

- [<span data-ttu-id="9d8f2-106">플러그형 프로토콜 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="9d8f2-106">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
