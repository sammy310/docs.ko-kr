---
description: '자세한 정보: 방법: HTTP 관련 속성에 액세스'
title: '방법: HTTP 관련 속성에 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: a54ef247b479cf6cdec8dc28732304cf03b0b202
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729304"
---
# <a name="how-to-access-http-specific-properties"></a><span data-ttu-id="06ee0-103">방법: HTTP 관련 속성에 액세스</span><span class="sxs-lookup"><span data-stu-id="06ee0-103">How to: Access HTTP-Specific Properties</span></span>

<span data-ttu-id="06ee0-104">이 샘플은 HTTP **Keep-alive** 동작을 끄고 웹 서버에서 프로토콜 버전 번호를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06ee0-104">This sample shows how to turn off the HTTP **Keep-alive** behavior and get the protocol version number from the Web server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06ee0-105">예제</span><span class="sxs-lookup"><span data-stu-id="06ee0-105">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="06ee0-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="06ee0-106">Compiling the Code</span></span>  

 <span data-ttu-id="06ee0-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06ee0-107">This example requires:</span></span>  
  
- <span data-ttu-id="06ee0-108">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="06ee0-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ee0-109">참조</span><span class="sxs-lookup"><span data-stu-id="06ee0-109">See also</span></span>

- [<span data-ttu-id="06ee0-110">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="06ee0-110">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="06ee0-111">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="06ee0-111">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="06ee0-112">HTTP</span><span class="sxs-lookup"><span data-stu-id="06ee0-112">HTTP</span></span>](http.md)
