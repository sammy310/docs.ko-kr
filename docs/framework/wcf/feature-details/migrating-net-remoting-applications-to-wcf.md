---
description: '자세한 정보: .NET Remoting 응용 프로그램을 WCF로 마이그레이션'
title: .NET Remoting 애플리케이션을 WCF로 마이그레이션
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 551ad759c11ab24d6ab83a466e8e94b8226bf4d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733764"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="550ce-103">.NET Remoting 애플리케이션을 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="550ce-103">Migrating .NET Remoting Applications to WCF</span></span>

<span data-ttu-id="550ce-104">**이 항목은 이전 버전의 기존 응용 프로그램과의 호환성을 위해 유지 되며 새로운 개발에는 권장 되지 않는 레거시 기술과 관련 되어 있습니다. 이제 WCF를 사용 하 여 배포 응용 프로그램을 개발 해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="550ce-104">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="550ce-105">기존 .NET Remoting 응용 프로그램에서 WCF를 활용 하는 방법에는 두 가지가 있습니다. 통합 및 마이그레이션.</span><span class="sxs-lookup"><span data-stu-id="550ce-105">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="550ce-106">통합을 사용 하면 .NET Remoting 2.0 및 WCF를 함께 실행 하 여 기존 .NET Remoting 2.0 코드를 수정 하지 않고도 두 기술 모두에 동일한 비즈니스 개체를 동시에 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-106">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="550ce-107">통합 하려면 .NET Framework 2.0 이상에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-107">Integration requires that you are running on .NET Framework 2.0 or greater.</span></span> <span data-ttu-id="550ce-108">WCF 기능을 활용 하려는 데 Remoting 2.0 시스템과의 유선 호환성이 필요 하지 않은 경우 전체 서비스를 WCF로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-108">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="550ce-109">.NET Remoting 2.0에서 WCF로 마이그레이션하려면 원격 개체의 인터페이스 및 해당 구성 설정을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-109">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="550ce-110">이러한 항목은 모두 [원격에서 Windows Communication Foundation로](/previous-versions/aa730857(v=vs.80))설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="550ce-110">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="550ce-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="550ce-111">See also</span></span>

- [<span data-ttu-id="550ce-112">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="550ce-112">Conceptual Overview</span></span>](../conceptual-overview.md)
