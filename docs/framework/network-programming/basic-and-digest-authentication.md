---
title: 기본 인증 및 다이제스트 인증
description: 애플리케이션에서 데이터를 요청하는 데 사용하는 WebRequest 개체에 사용자 이름과 암호를 제공하는 기본 다이제스트 인증을 사용하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
ms.openlocfilehash: 7772430b508b52a63d716550b69018385418c132
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502702"
---
# <a name="basic-and-digest-authentication"></a><span data-ttu-id="ca012-103">기본 인증 및 다이제스트 인증</span><span class="sxs-lookup"><span data-stu-id="ca012-103">Basic and Digest Authentication</span></span>
<span data-ttu-id="ca012-104">기본 및 다이제스트 인증의 <xref:System.Net> 구현은 RFC2617 – HTTP 인증을 준수합니다. 기본 및 다이제스트 인증([World Wide Web 컨소시엄](https://www.w3.org) 웹 사이트에서 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="ca012-104">The <xref:System.Net> implementation of basic and digest authentication complies with RFC2617 – HTTP Authentication: Basic and Digest Authentication (available on the [World Wide Web Consortium's](https://www.w3.org) website).</span></span>  
  
 <span data-ttu-id="ca012-105">기본 및 다이제스트 인증을 사용하려면 다음 예제와 같이 애플리케이션이 인터넷에서 데이터를 요청하는 데 사용하는 <xref:System.Net.WebRequest> 개체의 <xref:System.Net.WebRequest.Credentials%2A> 속성에 사용자 이름 및 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca012-105">To use basic and digest authentication, an application must provide a user name and password in the <xref:System.Net.WebRequest.Credentials%2A> property of the <xref:System.Net.WebRequest> object that it uses to request data from the Internet, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
> <span data-ttu-id="ca012-106">기본 및 다이제스트 인증과 함께 전송된 데이터는 암호화되지 않으므로 악의적 사용자가 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca012-106">Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary.</span></span> <span data-ttu-id="ca012-107">또한 기본 인증 자격 증명(사용자 이름 및 암호)은 일반 텍스트로 보내지므로 누군가 이를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca012-107">Additionally, Basic Authentication credentials (user name and password) are sent in the clear and can be intercepted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca012-108">참조</span><span class="sxs-lookup"><span data-stu-id="ca012-108">See also</span></span>

- [<span data-ttu-id="ca012-109">NTLM 및 Kerberos 인증</span><span class="sxs-lookup"><span data-stu-id="ca012-109">NTLM and Kerberos Authentication</span></span>](ntlm-and-kerberos-authentication.md)
- [<span data-ttu-id="ca012-110">인터넷 인증</span><span class="sxs-lookup"><span data-stu-id="ca012-110">Internet Authentication</span></span>](internet-authentication.md)
