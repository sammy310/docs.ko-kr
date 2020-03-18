---
title: FTP - .NET
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d945f03077a863d9e1baa6b59fe8a908566aba5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "61642882"
---
# <a name="ftp"></a><span data-ttu-id="7e46d-102">FTP</span><span class="sxs-lookup"><span data-stu-id="7e46d-102">FTP</span></span>

<span data-ttu-id="7e46d-103">.NET Framework에서는 <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스를 사용한 FTP 프로토콜을 포괄적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7e46d-103">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="7e46d-104">이러한 클래스는 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e46d-104">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="7e46d-105">대부분의 경우 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스는 요청을 만드는 데 필요한 모든 것을 제공하지만, 속성으로 노출되는 FTP별 기능에 액세스해야 할 경우 이러한 클래스를 <xref:System.Net.FtpWebRequest> 또는 <xref:System.Net.FtpWebResponse>로 형식 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e46d-105">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>

## <a name="examples"></a><span data-ttu-id="7e46d-106">예</span><span class="sxs-lookup"><span data-stu-id="7e46d-106">Examples</span></span>

<span data-ttu-id="7e46d-107">자세한 내용은 [방법: FTP를 사용하여 파일 다운로드](how-to-download-files-with-ftp.md), [방법: FTP를 사용하여 파일 업로드](how-to-upload-files-with-ftp.md) 및 [방법: FTP로 디렉터리 내용 나열](how-to-list-directory-contents-with-ftp.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e46d-107">For more information, see the following topics: [How to: Download Files with FTP](how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](how-to-list-directory-contents-with-ftp.md).</span></span>

## <a name="ftp-and-proxies"></a><span data-ttu-id="7e46d-108">FTP 및 프록시</span><span class="sxs-lookup"><span data-stu-id="7e46d-108">FTP and proxies</span></span>

<span data-ttu-id="7e46d-109"><xref:System.Net.FtpWebRequest.Proxy%2A> 속성으로 지정되는 프록시가 HTTP 프로시인 경우 <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> 및 <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> 명령만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e46d-109">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e46d-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e46d-110">See also</span></span>

- [<span data-ttu-id="7e46d-111">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="7e46d-111">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="7e46d-112">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="7e46d-112">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="7e46d-113">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="7e46d-113">Using Application Protocols</span></span>](using-application-protocols.md)
