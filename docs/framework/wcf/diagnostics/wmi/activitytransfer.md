---
description: '자세히 알아보기: ActivityTransfer'
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 28f7d1c0d1056327313e7aa6be293eb325d8f265
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99758010"
---
# <a name="activitytransfer"></a><span data-ttu-id="402b9-103">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="402b9-103">ActivityTransfer</span></span>

<span data-ttu-id="402b9-104">활동 전송 이벤트</span><span class="sxs-lookup"><span data-stu-id="402b9-104">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="402b9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="402b9-105">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="402b9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="402b9-106">Methods</span></span>  

 <span data-ttu-id="402b9-107">ActivityTransfer 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="402b9-107">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="402b9-108">속성</span><span class="sxs-lookup"><span data-stu-id="402b9-108">Properties</span></span>  

 <span data-ttu-id="402b9-109">ActivityTransfer 클래스에는 다음 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402b9-109">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="402b9-110">ActivityID</span><span class="sxs-lookup"><span data-stu-id="402b9-110">ActivityID</span></span>  
  
- <span data-ttu-id="402b9-111">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="402b9-111">Data type: object</span></span>  
    <span data-ttu-id="402b9-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="402b9-112">Access type: Read-only</span></span>  
  
- <span data-ttu-id="402b9-113">활동 ID</span><span class="sxs-lookup"><span data-stu-id="402b9-113">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="402b9-114">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="402b9-114">RelatedActivityID</span></span>  
  
- <span data-ttu-id="402b9-115">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="402b9-115">Data type: object</span></span>  
    <span data-ttu-id="402b9-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="402b9-116">Access type: Read-only</span></span>  
  
- <span data-ttu-id="402b9-117">관련 활동 ID</span><span class="sxs-lookup"><span data-stu-id="402b9-117">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="402b9-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="402b9-118">Requirements</span></span>  
  
|<span data-ttu-id="402b9-119">MOF</span><span class="sxs-lookup"><span data-stu-id="402b9-119">MOF</span></span>|<span data-ttu-id="402b9-120">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402b9-120">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="402b9-121">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="402b9-121">Namespace</span></span>|<span data-ttu-id="402b9-122">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="402b9-122">Defined in root\ServiceModel.</span></span>|
