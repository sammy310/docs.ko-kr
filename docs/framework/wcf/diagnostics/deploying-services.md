---
title: 서비스 배포
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 2c3cd17b597fafcd02b9155089bc583fafbc9dea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085764"
---
# <a name="deploying-services"></a><span data-ttu-id="e8536-102">서비스 배포</span><span class="sxs-lookup"><span data-stu-id="e8536-102">Deploying Services</span></span>
<span data-ttu-id="e8536-103">이 항목에서는 어떻게 런타임 환경에 Windows Communication Foundation (WCF) 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8536-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="e8536-104">응용 프로그램의 호스팅 환경 선택</span><span class="sxs-lookup"><span data-stu-id="e8536-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="e8536-105">WCF 서비스는 관리 코드를 지 모든 Windows 프로세스에서 실행 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8536-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="e8536-106">활성화할 서비스는 서비스를 만들고 컨텍스트와 수명을 제어하는 런타임 환경에 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8536-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="e8536-107">호스팅 옵션은 가장 간단한 콘솔 응용 프로그램에서 Windows 서비스, IIS(Internet Information Services), 또는 WAS(Windows Activation Service)에서 관리하는 작업자 프로세스 등의 서버 환경까지 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="e8536-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="e8536-108">WCF 응용 프로그램에 대 한 다양 한 호스팅 옵션을 검토 하려면 참조 [호스팅 서비스](../../../../docs/framework/wcf/hosting-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8536-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8536-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8536-109">See also</span></span>

- [<span data-ttu-id="e8536-110">호스팅</span><span class="sxs-lookup"><span data-stu-id="e8536-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)
- [<span data-ttu-id="e8536-111">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="e8536-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
