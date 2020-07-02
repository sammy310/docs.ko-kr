---
title: 인터넷 요청 만들기
description: 전달된 URI 스키마를 기반으로 파생 클래스를 만드는 WebRequest.Create 메서드를 통해 애플리케이션에서 WebRequest 인스턴스를 만드는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 389c7bf5969eca4322aa680a6f28dec0b899709a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325636"
---
# <a name="create-internet-requests"></a><span data-ttu-id="f98bd-103">인터넷 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="f98bd-103">Create internet requests</span></span>

<span data-ttu-id="f98bd-104">애플리케이션은 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 메서드를 통해 <xref:System.Net.WebRequest> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f98bd-104">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f98bd-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>는 전달된 URI 구성표에 따라 <xref:System.Net.WebRequest>에서 파생된 클래스를 만드는 정적 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f98bd-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> is a static method that creates a class derived from <xref:System.Net.WebRequest> based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="f98bd-106">웹, 파일 및 FTP 요청</span><span class="sxs-lookup"><span data-stu-id="f98bd-106">Web, file, and FTP requests</span></span>

<span data-ttu-id="f98bd-107">.NET Framework는 HTTP 및 HTTPS 요청을 처리하기 위해 `WebRequest`에서 파생된 <xref:System.Net.HttpWebRequest> 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f98bd-107">.NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from `WebRequest`, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="f98bd-108">대부분의 경우 `WebRequest` 클래스는 요청을 만드는 데 필요한 모든 속성을 제공합니다. 그러나 필요한 경우 `WebRequest.Create` 메서드를 통해 생성된 `WebRequest` 개체를 `HttpWebRequest` 형식에 캐스팅하여 요청의 HTTP 관련 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f98bd-108">In most cases, the `WebRequest` class provides all the properties you need to make a request; however, if necessary, you can cast `WebRequest` objects created by the `WebRequest.Create` method to the `HttpWebRequest` type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="f98bd-109">마찬가지로 `HttpWebResponse` 개체는 HTTP 및 HTTPS 요청의 응답을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f98bd-109">Similarly, the `HttpWebResponse` object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="f98bd-110">`HttpWebResponse` 개체의 HTTP 관련 속성에 액세스하려면 `WebResponse` 개체를 `HttpWebResponse` 형식에 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f98bd-110">To access the HTTP-specific properties of the `HttpWebResponse` object, you need to cast `WebResponse` objects to the `HttpWebResponse` type.</span></span>  
  
<span data-ttu-id="f98bd-111">또한 .NET Framework는 “file:”을 사용하는 리소스에 대한 요청을 처리하기 위해 <xref:System.Net.FileWebRequest> 및 <xref:System.Net.FileWebResponse> 클래스를 제공합니다. URI 구성표.</span><span class="sxs-lookup"><span data-stu-id="f98bd-111">.NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="f98bd-112">마찬가지로 “ftp:” 구성표를 사용하는 리소스에 대한 요청을 처리하기 위해 <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f98bd-112">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="f98bd-113">이러한 구성표를 사용하는 리소스에 대한 요청인 경우 `WebRequest.Create` 메서드를 사용하여 요청 생성에 사용할 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f98bd-113">If your request is for a resource that uses any of these schemes, you can use the `WebRequest.Create` method to obtain an object with which to make your request.</span></span>  
  
<span data-ttu-id="f98bd-114">다른 애플리케이션 수준 프로토콜을 사용하는 요청을 처리하려면 `WebRequest` 및 `WebResponse`에서 파생된 프로토콜별 클래스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f98bd-114">To handle requests that use other application-level protocols, implement protocol-specific classes derived from `WebRequest` and `WebResponse`.</span></span> <span data-ttu-id="f98bd-115">자세한 내용은 [플러그형 프로토콜 프로그래밍](programming-pluggable-protocols.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f98bd-115">For more information, see [Programming Pluggable Protocols](programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98bd-116">참조</span><span class="sxs-lookup"><span data-stu-id="f98bd-116">See also</span></span>

- [<span data-ttu-id="f98bd-117">방법: WebRequest 클래스를 사용하여 데이터 요청</span><span class="sxs-lookup"><span data-stu-id="f98bd-117">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="f98bd-118">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="f98bd-118">Requesting Data</span></span>](requesting-data.md)
