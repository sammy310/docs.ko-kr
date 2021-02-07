---
description: '자세한 정보: WCF 서비스 호스트의 자동 시작 제어'
title: WCF 서비스 호스트 자동 시작 제어
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: f0e9a4e79a403920c0bc6a512b30fb038b2aa1f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677394"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="4b964-103">WCF 서비스 호스트 자동 시작 제어</span><span class="sxs-lookup"><span data-stu-id="4b964-103">Controlling Auto-launching of WCF Service Host</span></span>

<span data-ttu-id="4b964-104">여러 프로젝트를 포함 하는 동일한 Visual Studio 솔루션에서 다른 프로젝트를 디버깅할 때 WCF 서비스 라이브러리 프로젝트에 대 한 Windows Communication Foundation (WCF) 서비스 호스트 (WcfSvcHost.exe)의 자동 시작 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b964-104">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="4b964-105">이렇게 하려면 **솔루션 탐색기** 에서 Wcf 서비스 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택한 다음 **WCF 옵션** 탭을 클릭 합니다. **동일한 솔루션에서 다른 프로젝트를 디버깅할 때 WCF 서비스 호스트 시작** 확인란은 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b964-105">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="4b964-106">동일한 솔루션에서 다른 프로젝트를 디버깅할 때이 특정 프로젝트에 대 한 WCF 서비스 호스트가 시작 되지 않도록이 확인란의 선택을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b964-106">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="4b964-107">이 동작은 F5 키를 사용한 디버깅이나 이 프로젝트의 서비스 참조 추가 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b964-107">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="4b964-108">이 옵션은 다음 프로젝트에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b964-108">This option is available to the following projects:</span></span>  
  
- <span data-ttu-id="4b964-109">WCF 서비스 라이브러리 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="4b964-109">WCF Service Library Project.</span></span>  
  
- <span data-ttu-id="4b964-110">순차 워크플로 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="4b964-110">Sequential Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="4b964-111">상태 시스템 워크플로 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="4b964-111">State Machine Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="4b964-112">배포 서비스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="4b964-112">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b964-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b964-113">See also</span></span>

- [<span data-ttu-id="4b964-114">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="4b964-114">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
