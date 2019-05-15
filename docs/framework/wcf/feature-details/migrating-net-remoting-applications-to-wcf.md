---
title: .NET Remoting 응용 프로그램을 WCF로 마이그레이션
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: c0ce7c9badc8bad6eedc58827b6efe2595ab2cf8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592871"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="4b064-102">.NET Remoting 응용 프로그램을 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4b064-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="4b064-103">**이 항목은 이전 버전의 기존 응용 프로그램과의 호환성을 위해 유지되며 새로운 개발에 권장되지 않는 레거시 기술과 관련된 것입니다. WCF를 사용 하 여 분산된 응용 프로그램을 개발할 수 해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4b064-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="4b064-104">두 가지 방법으로 기존.NET Remoting 응용 프로그램을 사용 하 여 WCF 활용 하기 위해: 통합과 마이그레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="4b064-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="4b064-105">통합을 사용 하면.NET Remoting 2.0와 나란히 실행, 기존.NET Remoting 2.0 코드를 수정 하지 않고도 동시에 두 기술을 모두를 통해 동일한 비즈니스 개체를 노출 하는 WCF 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b064-105">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="4b064-106">통합은.NET Framework 2.0 이상이 실행 되는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b064-106">Integration requires that you are running on .NET Framework 2.0 or greater.</span></span> <span data-ttu-id="4b064-107">WCF 기능을 활용 하려면을 Remoting 2.0 시스템과 유선 호환성 하지 않아도 wcf 전체 서비스를 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b064-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="4b064-108">원격 개체의 인터페이스 및 해당 구성 설정을 변경 해야 하는.NET Remoting 2.0에서 WCF로 마이그레이션.</span><span class="sxs-lookup"><span data-stu-id="4b064-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="4b064-109">이러한 항목에 나와 [From Remoting to the Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b064-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b064-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="4b064-110">See also</span></span>

- [<span data-ttu-id="4b064-111">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="4b064-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
