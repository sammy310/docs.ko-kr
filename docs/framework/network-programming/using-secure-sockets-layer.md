---
title: SSL(Secure Sockets Layer) 사용
description: System.Net 및 확장 클래스에서 SSL(Secure Sockets Layer)을 사용하여 .NET Framework의 여러 네트워크 프로토콜을 위한 연결을 암호화하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Networking
- SSL
- Secure Sockets Layer
- requesting data from Internet, Secure Sockets Layer
- sending data, Secure Sockets Layer
- Network Resources
- data requests, Secure Sockets Layer
- receiving data, Secure Sockets Layer
- Internet, Secure Sockets Layer
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
ms.openlocfilehash: 1309e9dc594869cec7bce81ef666d9f5e06f13b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265182"
---
# <a name="using-secure-sockets-layer"></a><span data-ttu-id="58acd-103">SSL(Secure Sockets Layer) 사용</span><span class="sxs-lookup"><span data-stu-id="58acd-103">Using Secure Sockets Layer</span></span>

<span data-ttu-id="58acd-104"><xref:System.Net> 클래스는 SSL(Secure Sockets Layer)을 사용하여 여러 네트워크 프로토콜에 대한 연결을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="58acd-104">The <xref:System.Net> classes use the Secure Sockets Layer (SSL) to encrypt the connection for several network protocols.</span></span>  
  
 <span data-ttu-id="58acd-105">HTTP 연결의 경우 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스는 SSL을 사용하여 SSL을 지원하는 웹 호스트와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="58acd-105">For http connections, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes use SSL to communicate with web hosts that support SSL.</span></span> <span data-ttu-id="58acd-106">제공된 URI에 따라 <xref:System.Net.WebRequest> 클래스가 SSL 사용을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="58acd-106">The decision to use SSL is made by the <xref:System.Net.WebRequest> class, based on the URI it is given.</span></span> <span data-ttu-id="58acd-107">URI가 “https:”로 시작하는 경우 SSL이 사용됩니다. URI가 “http:”로 시작하는 경우에는 암호화되지 않은 연결이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58acd-107">If the URI begins with "https:", SSL is used; if the URI begins with "http:", an unencrypted connection is used.</span></span>  
  
 <span data-ttu-id="58acd-108">FTP(파일 전송 프로토콜)와 함께 SSL을 사용하려면 <xref:System.Net.FtpWebRequest.GetResponse>를 호출하기 전에 <xref:System.Net.FtpWebRequest.EnableSsl> 속성을 true로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="58acd-108">To use SSL with File Transfer Protocol (FTP), set the <xref:System.Net.FtpWebRequest.EnableSsl> property to true prior to calling <xref:System.Net.FtpWebRequest.GetResponse>.</span></span> <span data-ttu-id="58acd-109">마찬가지로, SMTP(Simple Mail Transfer Protocol)와 함께 SSL을 사용하려면 이메일을 보내기 전에 <xref:System.Net.Mail.SmtpClient.EnableSsl> 속성을 true로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="58acd-109">Similarly, to use SSL with Simple Mail Transport Protocol (SMTP), set the <xref:System.Net.Mail.SmtpClient.EnableSsl> property to true prior to sending the email.</span></span>  
  
 <span data-ttu-id="58acd-110"><xref:System.Net.Security.SslStream> 클래스는 SSL에 대한 스트림 기반 추상화를 제공하고 SSL 핸드셰이크를 구성할 수 있는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58acd-110">The <xref:System.Net.Security.SslStream> class provides a stream-based abstraction for SSL, and offers many ways to configure the SSL handshake.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58acd-111">예제</span><span class="sxs-lookup"><span data-stu-id="58acd-111">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="58acd-112">코드</span><span class="sxs-lookup"><span data-stu-id="58acd-112">Code</span></span>  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="58acd-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="58acd-113">Compiling the Code</span></span>  

 <span data-ttu-id="58acd-114">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58acd-114">This example requires:</span></span>  
  
- <span data-ttu-id="58acd-115">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="58acd-115">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58acd-116">참조</span><span class="sxs-lookup"><span data-stu-id="58acd-116">See also</span></span>

- [<span data-ttu-id="58acd-117">네트워크 프로그래밍의 보안</span><span class="sxs-lookup"><span data-stu-id="58acd-117">Security in Network Programming</span></span>](security-in-network-programming.md)
- [<span data-ttu-id="58acd-118">.NET Framework의 네트워크 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="58acd-118">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="58acd-119">인증서 선택 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="58acd-119">Certificate Selection and Validation</span></span>](certificate-selection-and-validation.md)
