---
title: 지침 및 최선의 구현 방법
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, guidelines
- best practices [WCF], application design
- Windows Communication Foundation, best practices
- WCF, best practices
- Windows Communication Foundation, guidelines
ms.assetid: 5098ba46-6e8d-4e02-b0c5-d737f9fdad84
ms.openlocfilehash: 37e014aad44cf15e04ed3aa03a8367f5a44ceb96
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319806"
---
# <a name="guidelines-and-best-practices"></a><span data-ttu-id="e3ab7-102">지침 및 최선의 구현 방법</span><span class="sxs-lookup"><span data-stu-id="e3ab7-102">Guidelines and Best Practices</span></span>
<span data-ttu-id="e3ab7-103">이 섹션에는 WCF (Windows Communication Foundation) 응용 프로그램을 만들기 위한 지침을 제공 하는 항목이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ab7-103">This section contains topics that provide guidelines for creating Windows Communication Foundation (WCF) applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3ab7-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="e3ab7-104">In This Section</span></span>  
 [<span data-ttu-id="e3ab7-105">모범 사례: 데이터 계약 버전 관리</span><span class="sxs-lookup"><span data-stu-id="e3ab7-105">Best Practices: Data Contract Versioning</span></span>](best-practices-data-contract-versioning.md)  
 <span data-ttu-id="e3ab7-106">다음 버전 생성 시 손상되지 않는 데이터 계약을 만드는 방법 및 시점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ab7-106">Explains how and when to create data contracts that do not break when future versions are created.</span></span>  
  
 [<span data-ttu-id="e3ab7-107">서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="e3ab7-107">Service Versioning</span></span>](service-versioning.md)  
 <span data-ttu-id="e3ab7-108">WCF의 버전 관리를 고려 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ab7-108">Explains how to consider versioning in WCF.</span></span> <span data-ttu-id="e3ab7-109">예를 들어, 배포 후 서비스(및 노출된 엔드포인트)를 비즈니스 요구 사항 또는 IT 요구 사항 변경을 충족하거나 문제를 해결하기 위해 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ab7-109">After deployment, services (and the endpoints they expose) might need to be changed, for example, to satisfy changing business requirements or IT requirements, or to fix issues.</span></span> <span data-ttu-id="e3ab7-110">각 변경 작업에는 새 버전의 서비스가 도입됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3ab7-110">Each change introduces a new version of the service.</span></span>  
  
 [<span data-ttu-id="e3ab7-111">부하 분산</span><span class="sxs-lookup"><span data-stu-id="e3ab7-111">Load Balancing</span></span>](load-balancing.md)  
 <span data-ttu-id="e3ab7-112">웹 팜에서 부하 분산을 위한 지침을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3ab7-112">Lists guidelines for load balancing with a Web farm.</span></span>  
  
 [<span data-ttu-id="e3ab7-113">리소스 사용 제어 및 성능 향상</span><span class="sxs-lookup"><span data-stu-id="e3ab7-113">Controlling Resource Consumption and Improving Performance</span></span>](controlling-resource-consumption-and-improving-performance.md)  
 <span data-ttu-id="e3ab7-114">과도한 리소스 사용을 방지하고 보안을 향상시키는 데 도움을 주도록 디자인된 속성에 대해 설명하고, 이러한 속성 사용에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ab7-114">Describes the properties that are designed to help prevent undue resource consumption and improve security and points to more complete information about their use.</span></span>  
  
 [<span data-ttu-id="e3ab7-115">ClickOnce를 사용하여 WCF 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="e3ab7-115">Deploying WCF Applications with ClickOnce</span></span>](deploying-wcf-applications-with-clickonce.md)  
 <span data-ttu-id="e3ab7-116">ClickOnce 기능 사용 시 고려할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e3ab7-116">Describes the considerations to be made when using the ClickOnce feature.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e3ab7-117">참고</span><span class="sxs-lookup"><span data-stu-id="e3ab7-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="e3ab7-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e3ab7-118">Related Sections</span></span>  
 [<span data-ttu-id="e3ab7-119">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="e3ab7-119">Conceptual Overview</span></span>](conceptual-overview.md)  
  
 [<span data-ttu-id="e3ab7-120">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e3ab7-120">Basic WCF Programming</span></span>](basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3ab7-121">참조</span><span class="sxs-lookup"><span data-stu-id="e3ab7-121">See also</span></span>

- [<span data-ttu-id="e3ab7-122">Windows Communication Foundation 정의</span><span class="sxs-lookup"><span data-stu-id="e3ab7-122">What Is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="e3ab7-123">WCF (Windows Communication Foundation) 샘플</span><span class="sxs-lookup"><span data-stu-id="e3ab7-123">Windows Communication Foundation (WCF) samples</span></span>](./samples/index.md)
- [<span data-ttu-id="e3ab7-124">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="e3ab7-124">Conceptual Overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="e3ab7-125">클라이언트 빌드</span><span class="sxs-lookup"><span data-stu-id="e3ab7-125">Building Clients</span></span>](building-clients.md)
