---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENT_DATA'
title: COR_PRF_EVENT_DATA 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENT_DATA
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 477f36476deb9c0d74e263703e36b134c91b5327
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805569"
---
# <a name="cor_prf_event_data-enumeration"></a><span data-ttu-id="4233c-103">COR_PRF_EVENT_DATA 열거형</span><span class="sxs-lookup"><span data-stu-id="4233c-103">COR_PRF_EVENT_DATA Enumeration</span></span>

<span data-ttu-id="4233c-104">작성 중인 EventPipe 이벤트에 대 한 이벤트 데이터를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4233c-104">Describes the event data for an EventPipe event being written.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4233c-105">구문</span><span class="sxs-lookup"><span data-stu-id="4233c-105">Syntax</span></span>  
  
```cpp  
typedef struct
{
    UINT64 ptr;
    UINT32 size;
    UINT32 reserved;
} COR_PRF_EVENT_DATA;
```  
  
## <a name="members"></a><span data-ttu-id="4233c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4233c-106">Members</span></span>  
  
|<span data-ttu-id="4233c-107">멤버</span><span class="sxs-lookup"><span data-stu-id="4233c-107">Member</span></span>|<span data-ttu-id="4233c-108">설명</span><span class="sxs-lookup"><span data-stu-id="4233c-108">Description</span></span>|  
|------------|-----------------|  
|`ptr`|<span data-ttu-id="4233c-109">데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4233c-109">A pointer to the data.</span></span>|  
|`size`|<span data-ttu-id="4233c-110">가 가리키는 데이터의 크기입니다 `ptr` .</span><span class="sxs-lookup"><span data-stu-id="4233c-110">The size of the data pointed to by `ptr`.</span></span>|  
|`reserved`|<span data-ttu-id="4233c-111">예약 된 구현 특정 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="4233c-111">An reserved implementation specific field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4233c-112">설명</span><span class="sxs-lookup"><span data-stu-id="4233c-112">Remarks</span></span>  

 <span data-ttu-id="4233c-113">`COR_PRF_EVENT_DATA`이 구조는 [ICorProfilerInfo12:: EventPipeWriteEvent](icorprofilerinfo12-eventpipewriteevent-method.md) 메서드에서 작성 중인 이벤트에 대 한 데이터 페이로드를 프로 비전 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4233c-113">The `COR_PRF_EVENT_DATA` structure is used by the [ICorProfilerInfo12::EventPipeWriteEvent](icorprofilerinfo12-eventpipewriteevent-method.md) method to providate the data payload for the event being written.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4233c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4233c-114">Requirements</span></span>  

<span data-ttu-id="4233c-115">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4233c-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="4233c-116">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4233c-116">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4233c-117">참조</span><span class="sxs-lookup"><span data-stu-id="4233c-117">See also</span></span>

- [<span data-ttu-id="4233c-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="4233c-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="4233c-119">ICorProfilerInfo12::EventPipeWriteEvent</span><span class="sxs-lookup"><span data-stu-id="4233c-119">ICorProfilerInfo12::EventPipeWriteEvent</span></span>](icorprofilerinfo12-eventpipewriteevent-method.md)
