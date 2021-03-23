---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeWriteEvent 메서드'
title: 'ICorProfilerInfo12:: EventPipeWriteEvent 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeWriteEvent
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: a0a06ff0fa1c936518586834f4dfc73810ef0e44
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805742"
---
# <a name="icorprofilerinfo12eventpipewriteevent-method"></a><span data-ttu-id="3da4f-103">ICorProfilerInfo12:: EventPipeWriteEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="3da4f-103">ICorProfilerInfo12::EventPipeWriteEvent Method</span></span>

<span data-ttu-id="3da4f-104">이 이벤트를 사용 하도록 설정한 모든 수신기에 EventPipe 이벤트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="3da4f-104">Writes an EventPipe event to any listeners who have enabled this event.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3da4f-105">구문</span><span class="sxs-lookup"><span data-stu-id="3da4f-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeWriteEvent(
                [in] EVENTPIPE_EVENT    event,
                [in] UINT32             cData,
                [in, size_is(cData)]
                     COR_PRF_EVENT_DATA data[],
                [in] LPCGUID            pActivityId,
                [in] LPCGUID            pRelatedActivityId);
```  
  
## <a name="parameters"></a><span data-ttu-id="3da4f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3da4f-106">Parameters</span></span>

<span data-ttu-id="3da4f-107">`event` 진행 쓰여지는 이벤트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3da4f-107">`event` [in] The ID of the event being written.</span></span>

<span data-ttu-id="3da4f-108">`cData` 진행 의 요소 수 `data` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3da4f-108">`cData` [in] The number of elements in `data`.</span></span>

<span data-ttu-id="3da4f-109">`data` 진행 `COR_PRF_EVENT_DATA` 이벤트 인수를 포함 하는의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3da4f-109">`data` [in] An array of `COR_PRF_EVENT_DATA` containing the event arguments.</span></span>

<span data-ttu-id="3da4f-110">`pActivityId` 진행 이벤트의 작업 ID를 지정 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3da4f-110">`pActivityId` [in] A pointer to a GUID specifying the event's activity ID.</span></span>

<span data-ttu-id="3da4f-111">`pRelatedActivityId` 진행 이벤트의 관련 작업 ID를 지정 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3da4f-111">`pRelatedActivityId` [in] A pointer to a GUID specifying the event's related activity ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="3da4f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3da4f-112">Requirements</span></span>  

<span data-ttu-id="3da4f-113">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3da4f-113">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="3da4f-114">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3da4f-114">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3da4f-115">참조</span><span class="sxs-lookup"><span data-stu-id="3da4f-115">See also</span></span>

- [<span data-ttu-id="3da4f-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3da4f-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3da4f-117">ICorProfilerCallback10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3da4f-117">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="3da4f-118">ICorProfilerInfo12 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3da4f-118">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="3da4f-119">COR_PRF_EVENT_DATA 구조체</span><span class="sxs-lookup"><span data-stu-id="3da4f-119">COR_PRF_EVENT_DATA Structure</span></span>](cor-prf-event-data-structure.md)
