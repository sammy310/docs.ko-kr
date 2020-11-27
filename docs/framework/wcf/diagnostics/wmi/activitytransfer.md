---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291117"
---
# <a name="activitytransfer"></a><span data-ttu-id="1c984-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="1c984-102">ActivityTransfer</span></span>

<span data-ttu-id="1c984-103">활동 전송 이벤트</span><span class="sxs-lookup"><span data-stu-id="1c984-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c984-104">구문</span><span class="sxs-lookup"><span data-stu-id="1c984-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1c984-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1c984-105">Methods</span></span>  

 <span data-ttu-id="1c984-106">ActivityTransfer 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c984-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1c984-107">속성</span><span class="sxs-lookup"><span data-stu-id="1c984-107">Properties</span></span>  

 <span data-ttu-id="1c984-108">ActivityTransfer 클래스에는 다음 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c984-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="1c984-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="1c984-109">ActivityID</span></span>  
  
- <span data-ttu-id="1c984-110">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="1c984-110">Data type: object</span></span>  
    <span data-ttu-id="1c984-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1c984-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="1c984-112">활동 ID</span><span class="sxs-lookup"><span data-stu-id="1c984-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="1c984-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="1c984-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="1c984-114">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="1c984-114">Data type: object</span></span>  
    <span data-ttu-id="1c984-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1c984-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="1c984-116">관련 활동 ID</span><span class="sxs-lookup"><span data-stu-id="1c984-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c984-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c984-117">Requirements</span></span>  
  
|<span data-ttu-id="1c984-118">MOF</span><span class="sxs-lookup"><span data-stu-id="1c984-118">MOF</span></span>|<span data-ttu-id="1c984-119">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c984-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1c984-120">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="1c984-120">Namespace</span></span>|<span data-ttu-id="1c984-121">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c984-121">Defined in root\ServiceModel.</span></span>|
