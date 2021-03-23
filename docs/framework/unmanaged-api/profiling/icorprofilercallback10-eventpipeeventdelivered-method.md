---
description: '자세히 알아보기: ICorProfilerCallback10:: EventPipeEventDelivered 메서드'
title: 'ICorProfilerCallback10:: EventPipeEventDelivered 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10.EventPipeEventDelivered
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 7b2ca813d610c2b41d97d8cd76dac22ca38802d7
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805638"
---
# <a name="icorprofilercallback10eventpipeeventdelivered-method"></a><span data-ttu-id="a49c3-103">ICorProfilerCallback10:: EventPipeEventDelivered 메서드</span><span class="sxs-lookup"><span data-stu-id="a49c3-103">ICorProfilerCallback10::EventPipeEventDelivered Method</span></span>

<span data-ttu-id="a49c3-104">EventPipe 이벤트가 프로파일러의 현재 활성 세션에 전달 될 때마다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-104">Notifies the profiler whenever an EventPipe event has been delivered to the profiler's currently active session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a49c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="a49c3-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeEventDelivered(
        [in] EVENTPIPE_PROVIDER provider,
        [in] DWORD eventId,
        [in] DWORD eventVersion,
        [in] ULONG cbMetadataBlob,
        [in, size_is(cbMetadataBlob)] LPCBYTE metadataBlob,
        [in] ULONG cbEventData,
        [in, size_is(cbEventData)] LPCBYTE eventData,
        [in] LPCGUID pActivityId,
        [in] LPCGUID pRelatedActivityId,
        [in] ThreadID eventThread,
        [in] ULONG numStackFrames,
        [in, length_is(numStackFrames)] UINT_PTR stackFrames[]); 
```  
  
## <a name="parameters"></a><span data-ttu-id="a49c3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a49c3-106">Parameters</span></span>

<span data-ttu-id="a49c3-107">`provider` 진행 이 이벤트가 시작 된 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-107">`provider` [in] The provider that this event originated from.</span></span>

<span data-ttu-id="a49c3-108">`eventId` 진행 배달 되는 이벤트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-108">`eventId` [in] The ID of the event being delivered.</span></span>

<span data-ttu-id="a49c3-109">`eventVersion` 진행 전달 되는 이벤트의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-109">`eventVersion` [in] The version of the event being delivered.</span></span>

<span data-ttu-id="a49c3-110">`cbMetadataBlob` 진행 의 길이 (바이트)입니다 `metadataBlob` .</span><span class="sxs-lookup"><span data-stu-id="a49c3-110">`cbMetadataBlob` [in] The length, in bytes, of `metadataBlob`.</span></span>

<span data-ttu-id="a49c3-111">`metadataBlob` 진행 이벤트에 대 한 메타 데이터 blob에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-111">`metadataBlob` [in] A pointer to the metadata blob for the event.</span></span>

<span data-ttu-id="a49c3-112">`cbEventData` 진행 의 길이 (바이트)입니다 `eventData` .</span><span class="sxs-lookup"><span data-stu-id="a49c3-112">`cbEventData` [in] The length, in bytes, of `eventData`.</span></span>

<span data-ttu-id="a49c3-113">`eventData` 진행 이벤트에 대 한 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-113">`eventData` [in] The payload for the event.</span></span>

<span data-ttu-id="a49c3-114">`pActivityId` 진행 이벤트의 작업 ID 또는 NULL을 나타내는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-114">`pActivityId` [in] A pointer to the GUID that represents the event's activity ID, or NULL.</span></span>

<span data-ttu-id="a49c3-115">`pRelatedActivityId` 진행 이벤트의 관련 작업 ID 또는 NULL을 나타내는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-115">`pRelatedActivityId` [in] A pointer to the GUID that represents the event's related activity ID, or NULL.</span></span>

<span data-ttu-id="a49c3-116">`eventThread` 진행 이벤트가 발생 한 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-116">`eventThread` [in] The ID of the thread the event occurred on.</span></span>

<span data-ttu-id="a49c3-117">`numStackFrames` 진행 배열의 요소 수 `stackFrames` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-117">`numStackFrames` [in] The number of elements in the `stackFrames` array.</span></span>

<span data-ttu-id="a49c3-118">`stackFrames` 진행 이벤트의 관리 되는 호출 스택을 나타내는 코드 주소 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a49c3-118">`stackFrames` [in] An array of code addresses representing the managed callstack of the event.</span></span>

## <a name="requirements"></a><span data-ttu-id="a49c3-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a49c3-119">Requirements</span></span>  

<span data-ttu-id="a49c3-120">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a49c3-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="a49c3-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a49c3-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="a49c3-122">**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a49c3-122">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49c3-123">참조</span><span class="sxs-lookup"><span data-stu-id="a49c3-123">See also</span></span>

- [<span data-ttu-id="a49c3-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a49c3-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a49c3-125">ICorProfilerCallback10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a49c3-125">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="a49c3-126">ICorProfilerInfo12 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a49c3-126">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="a49c3-127">ICorProfilerInfo12 EventPipeStartSession 메서드</span><span class="sxs-lookup"><span data-stu-id="a49c3-127">ICorProfilerInfo12.EventPipeStartSession Method</span></span>](icorprofilerinfo12-eventpipestartsession-method.md)
