---
description: HttpsClientCertificateNotPresent에 대해 자세히 알아보세요.
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 1bca23915a55561c76b73c6b96750f324cb0e4dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99654488"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="05d3d-103">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="05d3d-103">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>

<span data-ttu-id="05d3d-104">클라이언트 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="05d3d-104">Client certificate is required.</span></span> <span data-ttu-id="05d3d-105">요청에서 인증서를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05d3d-105">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="05d3d-106">설명</span><span class="sxs-lookup"><span data-stu-id="05d3d-106">Description</span></span>  

 <span data-ttu-id="05d3d-107">이 추적은 HTTPS 수신기가 클라이언트 인증서에 연결되지 않은 HTTPS 요청을 받았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05d3d-107">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="05d3d-108">수신기가 모든 HTTPS 요청에서 클라이언트 인증서를 요구하도록 구성되어 있기 때문에 수신기가 클라이언트 인증의 유효성을 검사하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="05d3d-108">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d3d-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05d3d-109">See also</span></span>

- [<span data-ttu-id="05d3d-110">추적</span><span class="sxs-lookup"><span data-stu-id="05d3d-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="05d3d-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="05d3d-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="05d3d-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="05d3d-112">Administration and Diagnostics</span></span>](../index.md)
