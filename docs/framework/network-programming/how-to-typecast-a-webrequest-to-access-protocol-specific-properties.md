---
description: '자세한 정보: 방법: 프로토콜 관련 속성에 액세스하기 위해 WebRequest 형식 캐스팅'
title: '방법: 프로토콜 관련 속성에 액세스하기 위해 WebRequest 형식 캐스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: 24c07a3f2d77dec180476dec3c58f07b40e00c8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662743"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="eeec9-103">방법: 프로토콜 관련 속성에 액세스하기 위해 WebRequest 형식 캐스팅</span><span class="sxs-lookup"><span data-stu-id="eeec9-103">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>

<span data-ttu-id="eeec9-104">이 예제에서는 프로토콜별 속성에 액세스할 수 있도록 WebRequest를 형식 캐스팅하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eeec9-104">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeec9-105">예제</span><span class="sxs-lookup"><span data-stu-id="eeec9-105">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="eeec9-106">참조</span><span class="sxs-lookup"><span data-stu-id="eeec9-106">See also</span></span>

- [<span data-ttu-id="eeec9-107">플러그형 프로토콜 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="eeec9-107">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
