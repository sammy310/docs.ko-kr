---
title: WCF 라이브러리 프로젝트 배포
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: e3a90f03639a888b4528a1962a24b7adc5d43c58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260892"
---
# <a name="deploying-a-wcf-library-project"></a><span data-ttu-id="8dceb-102">WCF 라이브러리 프로젝트 배포</span><span class="sxs-lookup"><span data-stu-id="8dceb-102">Deploying a WCF Library Project</span></span>

<span data-ttu-id="8dceb-103">이 항목에서는 WCF (Windows Communication Foundation) 서비스 라이브러리 프로젝트를 배포할 수 있는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) Service Library Project.</span></span>  
  
## <a name="deploying-a-wcf-service-library"></a><span data-ttu-id="8dceb-104">WCF 서비스 라이브러리 배포</span><span class="sxs-lookup"><span data-stu-id="8dceb-104">Deploying a WCF Service Library</span></span>  

 <span data-ttu-id="8dceb-105">WCF 서비스 라이브러리는 DLL (동적 연결 라이브러리)입니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-105">A WCF service library is a dynamic-link library (DLL).</span></span> <span data-ttu-id="8dceb-106">따라서 자체적으로 실행될 수 없으며</span><span class="sxs-lookup"><span data-stu-id="8dceb-106">As such, it cannot be executed on its own.</span></span> <span data-ttu-id="8dceb-107">호스팅 환경에서 배포되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-107">It needs to be deployed into a hosting environment.</span></span> <span data-ttu-id="8dceb-108">이 프로세스에 대 한 자세한 내용은 [WCF 서비스 호스팅 및](/previous-versions/dotnet/articles/bb332338(v=msdn.10))사용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8dceb-108">For more information about this process, see [Hosting and Consuming WCF Services](/previous-versions/dotnet/articles/bb332338(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="8dceb-109">WCF 서비스 라이브러리는 다른 WCF 서비스와 마찬가지로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-109">A WCF service library can be deployed like any other WCF service.</span></span> <span data-ttu-id="8dceb-110">그러나 .NET Framework는 Dll에 대 한 구성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-110">However, be aware that .NET Framework does not support configuration for DLLs.</span></span> <span data-ttu-id="8dceb-111"><xref:System.Configuration>은 응용 프로그램 도메인당 하나의 구성 파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-111"><xref:System.Configuration> supports one configuration file per app-domain.</span></span> <span data-ttu-id="8dceb-112">WCF 서비스 라이브러리 프로젝트는 개발 중에 라이브러리에 대 한 App.config 파일을 제공 하 여 이러한 제한을 완화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-112">The WCF service library project alleviates this limitation by providing an App.config file for the library during development.</span></span> <span data-ttu-id="8dceb-113">그러나 App.config 파일은 배포 후에 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-113">However, the App.config file is not recognized after deployment.</span></span>  
  
 <span data-ttu-id="8dceb-114">구성 코드를 호스팅 환경에서 인식하는 구성 파일로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-114">You have to move your configuration code into the configuration file recognized by your hosting environment.</span></span> <span data-ttu-id="8dceb-115">자체 호스팅의 경우 App.config 파일의 내용을 호스팅 실행 파일의 App.config 파일에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-115">For self-hosting, you should copy the contents of the App.config file into the App.config file of the hosting executable.</span></span> <span data-ttu-id="8dceb-116">IIS를 사용하여 서비스를 호스팅하려면 App.config 파일의 내용을 가상 디렉터리의 Web.config 파일에 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dceb-116">If you use IIS to host your service, you should copy the contents of the App.config file into the Web.config file of the virtual directory.</span></span>
