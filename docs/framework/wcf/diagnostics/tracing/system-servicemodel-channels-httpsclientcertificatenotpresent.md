---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 15ae13563cfcfb3765559cafb2d31bd6482df7b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201184"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="53a03-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="53a03-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="53a03-103">클라이언트 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="53a03-103">Client certificate is required.</span></span> <span data-ttu-id="53a03-104">요청에서 인증서를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53a03-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="53a03-105">설명</span><span class="sxs-lookup"><span data-stu-id="53a03-105">Description</span></span>  
 <span data-ttu-id="53a03-106">이 추적은 HTTPS 수신기가 클라이언트 인증서에 연결되지 않은 HTTPS 요청을 받았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53a03-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="53a03-107">수신기가 모든 HTTPS 요청에서 클라이언트 인증서를 요구하도록 구성되어 있기 때문에 수신기가 클라이언트 인증의 유효성을 검사하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="53a03-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a03-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="53a03-108">See also</span></span>

- [<span data-ttu-id="53a03-109">추적</span><span class="sxs-lookup"><span data-stu-id="53a03-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="53a03-110">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="53a03-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="53a03-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="53a03-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
