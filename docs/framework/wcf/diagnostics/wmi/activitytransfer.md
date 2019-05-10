---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 6237d65d6964a4ebca34af895158c83239641593
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662818"
---
# <a name="activitytransfer"></a><span data-ttu-id="3e3fe-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="3e3fe-102">ActivityTransfer</span></span>
<span data-ttu-id="3e3fe-103">활동 전송 이벤트</span><span class="sxs-lookup"><span data-stu-id="3e3fe-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e3fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e3fe-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3e3fe-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3e3fe-105">Methods</span></span>  
 <span data-ttu-id="3e3fe-106">ActivityTransfer 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3fe-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3e3fe-107">속성</span><span class="sxs-lookup"><span data-stu-id="3e3fe-107">Properties</span></span>  
 <span data-ttu-id="3e3fe-108">ActivityTransfer 클래스에는 다음 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3fe-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="3e3fe-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="3e3fe-109">ActivityID</span></span>  
  
- <span data-ttu-id="3e3fe-110">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="3e3fe-110">Data type: object</span></span>  
    <span data-ttu-id="3e3fe-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3e3fe-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="3e3fe-112">작업 ID</span><span class="sxs-lookup"><span data-stu-id="3e3fe-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="3e3fe-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="3e3fe-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="3e3fe-114">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="3e3fe-114">Data type: object</span></span>  
    <span data-ttu-id="3e3fe-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3e3fe-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="3e3fe-116">관련 활동 ID</span><span class="sxs-lookup"><span data-stu-id="3e3fe-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e3fe-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e3fe-117">Requirements</span></span>  
  
|<span data-ttu-id="3e3fe-118">MOF</span><span class="sxs-lookup"><span data-stu-id="3e3fe-118">MOF</span></span>|<span data-ttu-id="3e3fe-119">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3fe-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3e3fe-120">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="3e3fe-120">Namespace</span></span>|<span data-ttu-id="3e3fe-121">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3fe-121">Defined in root\ServiceModel.</span></span>|
