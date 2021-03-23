---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENTPIPE_LEVEL'
title: COR_PRF_EVENTPIPE_LEVEL 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_LEVEL
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: da8211da1a9bb6262b078c5e56bee1d0c1f9342e
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805820"
---
# <a name="cor_prf_eventpipe_level-enumeration"></a><span data-ttu-id="2f4de-103">COR_PRF_EVENTPIPE_LEVEL 열거형</span><span class="sxs-lookup"><span data-stu-id="2f4de-103">COR_PRF_EVENTPIPE_LEVEL Enumeration</span></span>

<span data-ttu-id="2f4de-104">EventPipe 이벤트의 수준을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4de-104">Describes the level of an EventPipe event.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="2f4de-105">구문</span><span class="sxs-lookup"><span data-stu-id="2f4de-105">Syntax</span></span>  
  
```cpp  
typedef enum
{
    COR_PRF_EVENTPIPE_LOGALWAYS = 0,
    COR_PRF_EVENTPIPE_CRITICAL = 1,
    COR_PRF_EVENTPIPE_ERROR = 2,
    COR_PRF_EVENTPIPE_WARNING = 3,
    COR_PRF_EVENTPIPE_INFORMATIONAL = 4,
    COR_PRF_EVENTPIPE_VERBOSE = 5
} COR_PRF_EVENTPIPE_LEVEL;
```  
  
## <a name="members"></a><span data-ttu-id="2f4de-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2f4de-106">Members</span></span>  
  
|<span data-ttu-id="2f4de-107">멤버</span><span class="sxs-lookup"><span data-stu-id="2f4de-107">Member</span></span>|<span data-ttu-id="2f4de-108">설명</span><span class="sxs-lookup"><span data-stu-id="2f4de-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_EVENTPIPE_LOGALWAYS`|<span data-ttu-id="2f4de-109">이벤트는 항상 로깅됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f4de-109">The event is always logged.</span></span>|
|`COR_PRF_EVENTPIPE_CRITICAL`|<span data-ttu-id="2f4de-110">이벤트는 중요 한 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f4de-110">The event represents a critical message.</span></span>|
|`COR_PRF_EVENTPIPE_ERROR`|<span data-ttu-id="2f4de-111">이벤트는 오류 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f4de-111">The event represents an error message.</span></span>|
|`COR_PRF_EVENTPIPE_WARNING`|<span data-ttu-id="2f4de-112">이벤트는 경고 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f4de-112">The event represents a warning message.</span></span>|
|`COR_PRF_EVENTPIPE_INFORMATIONAL`|<span data-ttu-id="2f4de-113">이벤트는 정보 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f4de-113">The event represents an informational message.</span></span>|
|`COR_PRF_EVENTPIPE_VERBOSE`|<span data-ttu-id="2f4de-114">이벤트는 자세한 정보 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f4de-114">The event represents a verbose message.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="2f4de-115">설명</span><span class="sxs-lookup"><span data-stu-id="2f4de-115">Remarks</span></span>  

 <span data-ttu-id="2f4de-116">`COR_PRF_EVENTPIPE_LEVEL`열거형은 [ICorProfilerInfo12:: EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) 메서드에서 정의 되는 이벤트의 수준을 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f4de-116">The `COR_PRF_EVENTPIPE_LEVEL` enumeration is used by the [ICorProfilerInfo12::EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) method to indicate the level of the event being defined.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="2f4de-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f4de-117">Requirements</span></span>  

<span data-ttu-id="2f4de-118">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f4de-118">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="2f4de-119">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f4de-119">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f4de-120">참조</span><span class="sxs-lookup"><span data-stu-id="2f4de-120">See also</span></span>

- [<span data-ttu-id="2f4de-121">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="2f4de-121">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="2f4de-122">ICorProfilerInfo12::EventPipeDefineEvent</span><span class="sxs-lookup"><span data-stu-id="2f4de-122">ICorProfilerInfo12::EventPipeDefineEvent</span></span>](icorprofilerinfo12-eventpipedefineevent-method.md)
