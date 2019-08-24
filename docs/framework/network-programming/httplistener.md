---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
ms.openlocfilehash: d3fecb9fe78ca54f68d3c5a97dae5d5dd9fbb28d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075420"
---
# <a name="httplistener"></a><span data-ttu-id="692d6-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="692d6-102">HttpListener</span></span>
<span data-ttu-id="692d6-103"><xref:System.Net.HttpListener> 클래스는 프로그래밍 방식으로 제어되는 HTTP 프로토콜 수신기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="692d6-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="692d6-104">수신기는 <xref:System.Net.HttpListener> 개체의 수명 동안 활성화되며 애플리케이션 내에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="692d6-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="692d6-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="692d6-105">HTTP.SYS</span></span>  
 <span data-ttu-id="692d6-106"><xref:System.Net.HttpListener> 클래스는 Windows에 대한 모든 HTTP 트래픽을 처리하는 커널 모드 수신기인 HTTP.sys를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="692d6-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="692d6-107">HTTP.sys는 연결 관리, 대역폭 제한 및 웹 서버 로깅 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="692d6-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="692d6-108">`HttpCfg.exe` 도구를 사용하여 SSL 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="692d6-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="692d6-109">자세한 내용은 [서버](https://go.microsoft.com/fwlink/?LinkID=178285) 설명서의 [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) 도구에 대한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="692d6-109">For more information, see the documentation on the [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](https://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="692d6-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="692d6-110">See also</span></span>

- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpWebRequest>
- <xref:System.Net.HttpWebResponse>
- [<span data-ttu-id="692d6-111">HTTP 서버</span><span class="sxs-lookup"><span data-stu-id="692d6-111">HTTP Server</span></span>](https://go.microsoft.com/fwlink/?LinkID=178285)
- [<span data-ttu-id="692d6-112">인터넷 정보의 향상된 보안 기능</span><span class="sxs-lookup"><span data-stu-id="692d6-112">Security Enhancements in Internet Information</span></span>](https://go.microsoft.com/fwlink/?LinkID=178286)
- [<span data-ttu-id="692d6-113">HttpListener ASPX 호스트 애플리케이션 샘플</span><span class="sxs-lookup"><span data-stu-id="692d6-113">HttpListener ASPX Host Application Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179560)
- [<span data-ttu-id="692d6-114">HttpListener 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="692d6-114">HttpListener Technology Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179558)
- [<span data-ttu-id="692d6-115">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="692d6-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
