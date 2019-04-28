---
title: System.ServiceModel.Channels.HttpsClientCertificateInvalid
ms.date: 03/30/2017
ms.assetid: 8884dda1-fa0e-4d2a-8079-7042c51b64ef
ms.openlocfilehash: e8e405e4dfbe04634d0b71c6235f6f2e98fceced
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767230"
---
# <a name="systemservicemodelchannelshttpsclientcertificateinvalid"></a><span data-ttu-id="def9b-102">System.ServiceModel.Channels.HttpsClientCertificateInvalid</span><span class="sxs-lookup"><span data-stu-id="def9b-102">System.ServiceModel.Channels.HttpsClientCertificateInvalid</span></span>
<span data-ttu-id="def9b-103">클라이언트 인증서가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="def9b-103">Client certificate is invalid.</span></span>  
  
## <a name="description"></a><span data-ttu-id="def9b-104">설명</span><span class="sxs-lookup"><span data-stu-id="def9b-104">Description</span></span>  
 <span data-ttu-id="def9b-105">이 추적은 클라이언트가 제공한 인증서가 HTTPS 수신기에 의해 잘못된 것임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="def9b-105">This trace indicates that the certificate provided by the client was found to be invalid by the HTTPS listener.</span></span> <span data-ttu-id="def9b-106">HTTPS 수신기가 이 인증서를 사용하여 클라이언트 인증의 유효성 검사를 시도했습니다.</span><span class="sxs-lookup"><span data-stu-id="def9b-106">The HTTPS listener was attempting to validate the authenticity of the client using this certificate.</span></span> <span data-ttu-id="def9b-107">인증서의 인증 기관이 서비스를 호스팅하는 서버에 의해 인식되지 않을 경우 인증서가 잘못될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="def9b-107">A certificate could be invalid if its Certificate Authority is not recognized by the server hosting the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def9b-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="def9b-108">See also</span></span>

- [<span data-ttu-id="def9b-109">추적</span><span class="sxs-lookup"><span data-stu-id="def9b-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="def9b-110">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="def9b-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="def9b-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="def9b-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
