---
description: '자세한 정보: 방법: WebRequest를 사용하여 사용자 지정 프로토콜 등록'
title: '방법: WebRequest를 사용하여 사용자 지정 프로토콜 등록'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 7415017f20c0c6ed80570992e249fb8121907de2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785759"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="8076a-103">방법: WebRequest를 사용하여 사용자 지정 프로토콜 등록</span><span class="sxs-lookup"><span data-stu-id="8076a-103">How to: Register a Custom Protocol Using WebRequest</span></span>

<span data-ttu-id="8076a-104">이 예제에서는 다른 곳에서 정의된 프로토콜별 클래스를 등록하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8076a-104">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="8076a-105">이 예제에서 `CustomWebRequestCreator`는 `CustomWebRequest` 개체를 반환하는 **Create** 메서드를 구현하는 사용자가 구현한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8076a-105">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="8076a-106">코드 예제에서는 사용자 지정 프로토콜을 구현하는 `CustomWebRequest` 코드를 작성했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8076a-106">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8076a-107">예제</span><span class="sxs-lookup"><span data-stu-id="8076a-107">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8076a-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8076a-108">Compiling the Code</span></span>  

 <span data-ttu-id="8076a-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8076a-109">This example requires:</span></span>  
  
 <span data-ttu-id="8076a-110"><xref:System.Net> 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="8076a-110">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8076a-111">참조</span><span class="sxs-lookup"><span data-stu-id="8076a-111">See also</span></span>

- [<span data-ttu-id="8076a-112">플러그형 프로토콜 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8076a-112">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
