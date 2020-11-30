---
title: '방법: HTTP 관련 속성에 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: ea709bba17d4e2f00b760c8713f9e8100496f0bf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250517"
---
# <a name="how-to-access-http-specific-properties"></a><span data-ttu-id="303fb-102">방법: HTTP 관련 속성에 액세스</span><span class="sxs-lookup"><span data-stu-id="303fb-102">How to: Access HTTP-Specific Properties</span></span>

<span data-ttu-id="303fb-103">이 샘플은 HTTP **Keep-alive** 동작을 끄고 웹 서버에서 프로토콜 버전 번호를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="303fb-103">This sample shows how to turn off the HTTP **Keep-alive** behavior and get the protocol version number from the Web server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="303fb-104">예제</span><span class="sxs-lookup"><span data-stu-id="303fb-104">Example</span></span>  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="303fb-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="303fb-105">Compiling the Code</span></span>  

 <span data-ttu-id="303fb-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="303fb-106">This example requires:</span></span>  
  
- <span data-ttu-id="303fb-107">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="303fb-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303fb-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="303fb-108">See also</span></span>

- [<span data-ttu-id="303fb-109">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="303fb-109">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="303fb-110">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="303fb-110">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="303fb-111">HTTP</span><span class="sxs-lookup"><span data-stu-id="303fb-111">HTTP</span></span>](http.md)
