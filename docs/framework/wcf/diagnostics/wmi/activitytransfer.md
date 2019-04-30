---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964297"
---
# <a name="activitytransfer"></a><span data-ttu-id="28e43-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="28e43-102">ActivityTransfer</span></span>
<span data-ttu-id="28e43-103">활동 전송 이벤트</span><span class="sxs-lookup"><span data-stu-id="28e43-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28e43-104">구문</span><span class="sxs-lookup"><span data-stu-id="28e43-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="28e43-105">메서드</span><span class="sxs-lookup"><span data-stu-id="28e43-105">Methods</span></span>  
 <span data-ttu-id="28e43-106">ActivityTransfer 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28e43-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="28e43-107">속성</span><span class="sxs-lookup"><span data-stu-id="28e43-107">Properties</span></span>  
 <span data-ttu-id="28e43-108">ActivityTransfer 클래스에는 다음 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28e43-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="28e43-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="28e43-109">ActivityID</span></span>  
  
- <span data-ttu-id="28e43-110">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="28e43-110">Data type: object</span></span>  
    <span data-ttu-id="28e43-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="28e43-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="28e43-112">작업 ID</span><span class="sxs-lookup"><span data-stu-id="28e43-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="28e43-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="28e43-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="28e43-114">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="28e43-114">Data type: object</span></span>  
    <span data-ttu-id="28e43-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="28e43-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="28e43-116">관련 활동 ID</span><span class="sxs-lookup"><span data-stu-id="28e43-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28e43-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28e43-117">Requirements</span></span>  
  
|<span data-ttu-id="28e43-118">MOF</span><span class="sxs-lookup"><span data-stu-id="28e43-118">MOF</span></span>|<span data-ttu-id="28e43-119">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28e43-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="28e43-120">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="28e43-120">Namespace</span></span>|<span data-ttu-id="28e43-121">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28e43-121">Defined in root\ServiceModel.</span></span>|
