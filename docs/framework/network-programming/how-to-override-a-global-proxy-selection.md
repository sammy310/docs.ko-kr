---
title: '방법: 전역 프록시 선택 재정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 44845fb67aac4ff9ab9dda8cf4934153c8c4f23c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048266"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="a0173-102">방법: 전역 프록시 선택 재정의</span><span class="sxs-lookup"><span data-stu-id="a0173-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="a0173-103">이 예제에서는 글로벌 프록시 선택을 포트 80의 **라는 프록시 서버로 재정의하는** WebRequest`www.contoso.com`를 `alternateproxy`에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a0173-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0173-104">예제</span><span class="sxs-lookup"><span data-stu-id="a0173-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0173-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a0173-105">Compiling the Code</span></span>  
 <span data-ttu-id="a0173-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a0173-106">This example requires:</span></span>  
  
- <span data-ttu-id="a0173-107">[System.Net`using` 네임스페이스에 대한 ](../../csharp/language-reference/keywords/using-directive.md) **지시문**</span><span class="sxs-lookup"><span data-stu-id="a0173-107">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0173-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0173-108">See also</span></span>

- [<span data-ttu-id="a0173-109">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="a0173-109">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="a0173-110">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="a0173-110">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
