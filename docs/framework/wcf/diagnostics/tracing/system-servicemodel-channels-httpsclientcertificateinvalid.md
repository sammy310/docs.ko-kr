---
description: HttpsClientCertificateInvalid에 대해 자세히 알아보세요.
title: System.ServiceModel.Channels.HttpsClientCertificateInvalid
ms.date: 03/30/2017
ms.assetid: 8884dda1-fa0e-4d2a-8079-7042c51b64ef
ms.openlocfilehash: c9d6545beee55000dc609c68824f27e33b71f60f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635235"
---
# <a name="systemservicemodelchannelshttpsclientcertificateinvalid"></a><span data-ttu-id="cff19-103">System.ServiceModel.Channels.HttpsClientCertificateInvalid</span><span class="sxs-lookup"><span data-stu-id="cff19-103">System.ServiceModel.Channels.HttpsClientCertificateInvalid</span></span>

<span data-ttu-id="cff19-104">클라이언트 인증서가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cff19-104">Client certificate is invalid.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cff19-105">설명</span><span class="sxs-lookup"><span data-stu-id="cff19-105">Description</span></span>  

 <span data-ttu-id="cff19-106">이 추적은 클라이언트가 제공한 인증서가 HTTPS 수신기에 의해 잘못된 것임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cff19-106">This trace indicates that the certificate provided by the client was found to be invalid by the HTTPS listener.</span></span> <span data-ttu-id="cff19-107">HTTPS 수신기가 이 인증서를 사용하여 클라이언트 인증의 유효성 검사를 시도했습니다.</span><span class="sxs-lookup"><span data-stu-id="cff19-107">The HTTPS listener was attempting to validate the authenticity of the client using this certificate.</span></span> <span data-ttu-id="cff19-108">인증서의 인증 기관이 서비스를 호스팅하는 서버에 의해 인식되지 않을 경우 인증서가 잘못될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff19-108">A certificate could be invalid if its Certificate Authority is not recognized by the server hosting the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff19-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cff19-109">See also</span></span>

- [<span data-ttu-id="cff19-110">추적</span><span class="sxs-lookup"><span data-stu-id="cff19-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="cff19-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="cff19-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="cff19-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="cff19-112">Administration and Diagnostics</span></span>](../index.md)
