---
title: '방법: 글로벌 프록시 선택 재정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: e5f4dc22ad75dc4d4f7dc30f44e6ae304403ef16
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914524"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="157ac-102">방법: 글로벌 프록시 선택 재정의</span><span class="sxs-lookup"><span data-stu-id="157ac-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="157ac-103">이 예제에서는 글로벌 프록시 선택을 포트 80의 `alternateproxy`라는 프록시 서버로 재정의하는 **WebRequest**를 `www.contoso.com`에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="157ac-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="157ac-104">예제</span><span class="sxs-lookup"><span data-stu-id="157ac-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="157ac-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="157ac-105">Compiling the Code</span></span>  
 <span data-ttu-id="157ac-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="157ac-106">This example requires:</span></span>  
  
- <span data-ttu-id="157ac-107">**System.Net** 네임스페이스에 대한 [`using` 지시문](../../csharp/language-reference/keywords/using-directive.md)</span><span class="sxs-lookup"><span data-stu-id="157ac-107">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="157ac-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="157ac-108">See also</span></span>

- [<span data-ttu-id="157ac-109">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="157ac-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="157ac-110">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="157ac-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
