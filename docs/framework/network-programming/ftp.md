---
title: FTP - .NET
description: .NET Framework에서 FtpWebRequest 및 FtpWebResponse 클래스를 사용하여 FTP 프로토콜에 대해 제공하는 포괄적인 지원에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d21ca43cd1041df358dc5e2add9560fb33e85d83
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502589"
---
# <a name="ftp"></a><span data-ttu-id="c838b-103">FTP</span><span class="sxs-lookup"><span data-stu-id="c838b-103">FTP</span></span>

<span data-ttu-id="c838b-104">.NET Framework에서는 <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스를 사용한 FTP 프로토콜을 포괄적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-104">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="c838b-105">이러한 클래스는 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-105">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="c838b-106">대부분의 경우 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스는 요청을 만드는 데 필요한 모든 것을 제공하지만, 속성으로 노출되는 FTP별 기능에 액세스해야 할 경우 이러한 클래스를 <xref:System.Net.FtpWebRequest> 또는 <xref:System.Net.FtpWebResponse>로 형식 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-106">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>

## <a name="examples"></a><span data-ttu-id="c838b-107">예</span><span class="sxs-lookup"><span data-stu-id="c838b-107">Examples</span></span>

<span data-ttu-id="c838b-108">자세한 내용은 다음 항목을 참조하세요. [방법: FTP를 사용하여 파일 다운로드](how-to-download-files-with-ftp.md), [방법: FTP를 사용하여 파일 업로드](how-to-upload-files-with-ftp.md), [방법: FTP를 사용하여 디렉터리 내용 나열](how-to-list-directory-contents-with-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="c838b-108">For more information, see the following topics: [How to: Download Files with FTP](how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](how-to-list-directory-contents-with-ftp.md).</span></span>

## <a name="ftp-and-proxies"></a><span data-ttu-id="c838b-109">FTP 및 프록시</span><span class="sxs-lookup"><span data-stu-id="c838b-109">FTP and proxies</span></span>

<span data-ttu-id="c838b-110"><xref:System.Net.FtpWebRequest.Proxy%2A> 속성으로 지정되는 프록시가 HTTP 프로시인 경우 <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> 및 <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> 명령만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c838b-110">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="c838b-111">참조</span><span class="sxs-lookup"><span data-stu-id="c838b-111">See also</span></span>

- [<span data-ttu-id="c838b-112">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="c838b-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="c838b-113">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="c838b-113">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="c838b-114">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="c838b-114">Using Application Protocols</span></span>](using-application-protocols.md)
