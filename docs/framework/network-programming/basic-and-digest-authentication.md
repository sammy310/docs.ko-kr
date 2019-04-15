---
title: 기본 인증 및 다이제스트 인증
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
ms.openlocfilehash: 4f70d2aef3bb064a3df9db9c87671040776332a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089824"
---
# <a name="basic-and-digest-authentication"></a><span data-ttu-id="04e10-102">기본 인증 및 다이제스트 인증</span><span class="sxs-lookup"><span data-stu-id="04e10-102">Basic and Digest Authentication</span></span>
<span data-ttu-id="04e10-103">기본 및 다이제스트 인증의 <xref:System.Net> 구현은 RFC2617 – HTTP 인증을 준수합니다. 기본 및 다이제스트 인증([World Wide Web 컨소시엄](https://www.w3.org) 웹 사이트에서 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="04e10-103">The <xref:System.Net> implementation of basic and digest authentication complies with RFC2617 – HTTP Authentication: Basic and Digest Authentication (available on the [World Wide Web Consortium's](https://www.w3.org) website).</span></span>  
  
 <span data-ttu-id="04e10-104">기본 및 다이제스트 인증을 사용하려면 다음 예제와 같이 애플리케이션이 인터넷에서 데이터를 요청하는 데 사용하는 <xref:System.Net.WebRequest> 개체의 <xref:System.Net.WebRequest.Credentials%2A> 속성에 사용자 이름 및 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e10-104">To use basic and digest authentication, an application must provide a user name and password in the <xref:System.Net.WebRequest.Credentials%2A> property of the <xref:System.Net.WebRequest> object that it uses to request data from the Internet, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="04e10-105">기본 및 다이제스트 인증과 함께 전송된 데이터는 암호화되지 않으므로 악의적 사용자가 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04e10-105">Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary.</span></span> <span data-ttu-id="04e10-106">또한 기본 인증 자격 증명(사용자 이름 및 암호)은 일반 텍스트로 보내지므로 누군가 이를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04e10-106">Additionally, Basic Authentication credentials (user name and password) are sent in the clear and can be intercepted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e10-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04e10-107">See also</span></span>

- [<span data-ttu-id="04e10-108">NTLM 및 Kerberos 인증</span><span class="sxs-lookup"><span data-stu-id="04e10-108">NTLM and Kerberos Authentication</span></span>](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)
- [<span data-ttu-id="04e10-109">인터넷 인증</span><span class="sxs-lookup"><span data-stu-id="04e10-109">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
