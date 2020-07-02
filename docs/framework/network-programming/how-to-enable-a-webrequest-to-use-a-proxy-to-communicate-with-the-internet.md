---
title: '방법: 프록시를 사용하여 인터넷과 통신하도록 WebRequest 설정'
description: .NET Framework에서 모든 WebRequest가 프록시를 사용하여 인터넷과 통신하도록 전역 프록시 인스턴스를 만드는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 0fc33cea3f5a7fe4669b110e53e71afdb9561c23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502537"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="882fb-103">방법: 프록시를 사용하여 인터넷과 통신하도록 WebRequest 설정</span><span class="sxs-lookup"><span data-stu-id="882fb-103">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>

<span data-ttu-id="882fb-104">이 예제에서는 인터넷과 통신하는 데 프록시를 사용하기 위해 <xref:System.Net.WebRequest>를 사용하도록 설정할 전역 프록시 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="882fb-104">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="882fb-105">예제에서는 프록시 서버의 이름이 `webproxy`이고 표준 HTTP 포트인 포트 80에서 통신한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="882fb-105">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>

## <a name="example"></a><span data-ttu-id="882fb-106">예제</span><span class="sxs-lookup"><span data-stu-id="882fb-106">Example</span></span>

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a><span data-ttu-id="882fb-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="882fb-107">Compiling the Code</span></span>

<span data-ttu-id="882fb-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="882fb-108">This example requires:</span></span>

- <span data-ttu-id="882fb-109">**System.Net** 네임스페이스에 대한 C# [`using` 지시문](../../csharp/language-reference/keywords/using-directive.md)</span><span class="sxs-lookup"><span data-stu-id="882fb-109">A C# [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>
- <span data-ttu-id="882fb-110">**System.Net** 네임스페이스에 대한 Visual Basic [`Imports` 문](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span><span class="sxs-lookup"><span data-stu-id="882fb-110">A Visual Basic [`Imports` statement](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the **System.Net** namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="882fb-111">참조</span><span class="sxs-lookup"><span data-stu-id="882fb-111">See also</span></span>

- [<span data-ttu-id="882fb-112">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="882fb-112">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="882fb-113">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="882fb-113">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
