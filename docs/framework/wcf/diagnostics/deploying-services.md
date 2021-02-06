---
description: '자세한 정보: 서비스 배포'
title: 서비스 배포
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 6a0b1d88410b865f57cd1eb16f070842a75ddb07
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99645999"
---
# <a name="deploying-services"></a><span data-ttu-id="c0cbb-103">서비스 배포</span><span class="sxs-lookup"><span data-stu-id="c0cbb-103">Deploying Services</span></span>

<span data-ttu-id="c0cbb-104">이 항목에서는 런타임 환경에 WCF (Windows Communication Foundation) 응용 프로그램을 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0cbb-104">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="c0cbb-105">애플리케이션의 호스팅 환경 선택</span><span class="sxs-lookup"><span data-stu-id="c0cbb-105">Choosing the Hosting Environment for Your Application</span></span>  

 <span data-ttu-id="c0cbb-106">WCF 서비스는 관리 코드를 지 원하는 모든 Windows 프로세스에서 실행 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c0cbb-106">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="c0cbb-107">활성화할 서비스는 서비스를 만들고 컨텍스트와 수명을 제어하는 런타임 환경에 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0cbb-107">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="c0cbb-108">호스팅 옵션은 가장 간단한 콘솔 애플리케이션에서 Windows 서비스, IIS(Internet Information Services), 또는 WAS(Windows Activation Service)에서 관리하는 작업자 프로세스 등의 서버 환경까지 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="c0cbb-108">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="c0cbb-109">WCF 응용 프로그램에 대 한 다양 한 호스팅 옵션을 검토 하려면 [호스팅 서비스](../hosting-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0cbb-109">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0cbb-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0cbb-110">See also</span></span>

- [<span data-ttu-id="c0cbb-111">호스팅</span><span class="sxs-lookup"><span data-stu-id="c0cbb-111">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="c0cbb-112">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="c0cbb-112">Hosting Services</span></span>](../hosting-services.md)
