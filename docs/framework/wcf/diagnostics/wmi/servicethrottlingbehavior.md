---
description: '자세히 알아보기: ServiceThrottlingBehavior'
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: c4cf354c96340b910807bf7904e63a08dc01764b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715446"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="3a875-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="3a875-103">ServiceThrottlingBehavior</span></span>

<span data-ttu-id="3a875-104">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="3a875-104">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a875-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a875-105">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3a875-106">메서드</span><span class="sxs-lookup"><span data-stu-id="3a875-106">Methods</span></span>  

 <span data-ttu-id="3a875-107">ServiceThrottlingBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a875-107">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3a875-108">속성</span><span class="sxs-lookup"><span data-stu-id="3a875-108">Properties</span></span>  

 <span data-ttu-id="3a875-109">ServiceThrottlingBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a875-109">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="3a875-110">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="3a875-110">MaxConcurrentCalls</span></span>  

 <span data-ttu-id="3a875-111">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="3a875-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="3a875-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3a875-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a875-113">ServiceHost의 모든 디스패처 개체에서 동시에 처리하는 최대 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a875-113">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="3a875-114">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="3a875-114">MaxConcurrentInstances</span></span>  

 <span data-ttu-id="3a875-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="3a875-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="3a875-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3a875-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a875-117">한 번에 실행할 수 있는 최대 서비스 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a875-117">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="3a875-118">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="3a875-118">MaxConcurrentSessions</span></span>  

 <span data-ttu-id="3a875-119">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="3a875-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="3a875-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3a875-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a875-121">호스트가 한 번에 수락할 수 있는 최대 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a875-121">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a875-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a875-122">Requirements</span></span>  
  
|<span data-ttu-id="3a875-123">MOF</span><span class="sxs-lookup"><span data-stu-id="3a875-123">MOF</span></span>|<span data-ttu-id="3a875-124">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a875-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3a875-125">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="3a875-125">Namespace</span></span>|<span data-ttu-id="3a875-126">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a875-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a875-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a875-127">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
