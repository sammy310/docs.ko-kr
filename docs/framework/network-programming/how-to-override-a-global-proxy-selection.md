---
title: '방법: 글로벌 프록시 선택 재정의'
description: 이 예제에 따라 WebRequest를 URL에 보내 프록시 서버를 사용한 선택을 재정의함으로써 전역 프록시 선택을 재정의합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 8931cdc471b957447277c333ba482a0cec0e6aa5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265741"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="58e84-103">방법: 글로벌 프록시 선택 재정의</span><span class="sxs-lookup"><span data-stu-id="58e84-103">How to: Override a Global Proxy Selection</span></span>

<span data-ttu-id="58e84-104">이 예제에서는 글로벌 프록시 선택을 포트 80의 `alternateproxy`라는 프록시 서버로 재정의하는 **WebRequest** 를 `www.contoso.com`에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="58e84-104">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58e84-105">예제</span><span class="sxs-lookup"><span data-stu-id="58e84-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="58e84-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="58e84-106">Compiling the Code</span></span>  

 <span data-ttu-id="58e84-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58e84-107">This example requires:</span></span>  
  
- <span data-ttu-id="58e84-108">**System.Net** 네임스페이스에 대한 [`using` 지시문](../../csharp/language-reference/keywords/using-directive.md)</span><span class="sxs-lookup"><span data-stu-id="58e84-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e84-109">참조</span><span class="sxs-lookup"><span data-stu-id="58e84-109">See also</span></span>

- [<span data-ttu-id="58e84-110">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="58e84-110">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="58e84-111">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="58e84-111">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
