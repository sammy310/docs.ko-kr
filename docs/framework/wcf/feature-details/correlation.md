---
description: '자세히 알아보기: 상관 관계'
title: 상관 관계
ms.date: 03/30/2017
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
ms.openlocfilehash: c4142a4e7c9472eaf52fc5339221bb59c1883f9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780364"
---
# <a name="correlation"></a><span data-ttu-id="11d52-103">상관 관계</span><span class="sxs-lookup"><span data-stu-id="11d52-103">Correlation</span></span>

<span data-ttu-id="11d52-104">워크플로 서비스 애플리케이션이 다른 서비스와 통신할 때는 둘 사이의 메시지가 적절한 워크플로 인스턴스에 디스패치되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11d52-104">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="11d52-105">상관 관계는 이를 위한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11d52-105">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="11d52-106">이 단원의 항목에서는 상관 관계의 개요를 제공하고 다양한 워크플로 서비스 시나리오에서 상관 관계를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11d52-106">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11d52-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="11d52-107">In This Section</span></span>  

 [<span data-ttu-id="11d52-108">상관 관계 개요</span><span class="sxs-lookup"><span data-stu-id="11d52-108">Correlation Overview</span></span>](correlation-overview.md)  
 <span data-ttu-id="11d52-109">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]에서 사용할 수 있는 상관 관계의 형식에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11d52-109">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="11d52-110">영속 이중</span><span class="sxs-lookup"><span data-stu-id="11d52-110">Durable Duplex</span></span>](durable-duplex-correlation.md)  
 <span data-ttu-id="11d52-111">영속 이중 상관 관계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11d52-111">Describes durable duplex correlation.</span></span>
  
 [<span data-ttu-id="11d52-112">요청-회신</span><span class="sxs-lookup"><span data-stu-id="11d52-112">Request-Reply</span></span>](request-reply-correlation.md)  
 <span data-ttu-id="11d52-113">요청-회신 상관 관계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11d52-113">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="11d52-114">상관 관계 문제 해결</span><span class="sxs-lookup"><span data-stu-id="11d52-114">Troubleshooting Correlation</span></span>](troubleshooting-correlation.md)  
 <span data-ttu-id="11d52-115">상관 관계 문제를 해결하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11d52-115">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d52-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11d52-116">See also</span></span>

- <xref:System.ServiceModel.Activities.CorrelationHandle>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.Receive>
- <xref:System.ServiceModel.CorrelationQuery>
