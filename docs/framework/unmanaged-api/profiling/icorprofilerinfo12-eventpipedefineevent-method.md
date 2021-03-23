---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeDefineEvent 메서드'
title: 'ICorProfilerInfo12:: EventPipeDefineEvent 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeDefineEvent
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 845f7f26dce7aa0f4b7d895b9f04cc89e7ac7192
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805755"
---
# <a name="icorprofilerinfo12eventpipedefineevent-method"></a><span data-ttu-id="e8b89-103">ICorProfilerInfo12:: EventPipeDefineEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="e8b89-103">ICorProfilerInfo12::EventPipeDefineEvent Method</span></span>

<span data-ttu-id="e8b89-104">기존 공급자의 EventPipe 이벤트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-104">Defines an EventPipe event on an existing provider.</span></span> <span data-ttu-id="e8b89-105">이 공급자는 다른 수신기가 받을 수 있는 EventPipe 이벤트를 작성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-105">This provider can be used to write EventPipe events that other listeners can receive.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e8b89-106">구문</span><span class="sxs-lookup"><span data-stu-id="e8b89-106">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeDefineEvent(
                [in] EVENTPIPE_PROVIDER     provider,
                [in, string] const WCHAR   *eventName,
                [in] UINT32                 eventID,
                [in] UINT64                 keywords,
                [in] UINT32                 eventVersion,
                [in] UINT32                 level,
                [in] UINT8                  opcode,
                [in] BOOL                   needStack,
                [in] UINT32                 cParamDescs,
                [in, size_is(cParamDescs)]
                     COR_PRF_EVENTPIPE_PARAM_DESC pParamDescs[],
                [out] EVENTPIPE_EVENT      *pEvent);
```  
  
## <a name="parameters"></a><span data-ttu-id="e8b89-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e8b89-107">Parameters</span></span>

<span data-ttu-id="e8b89-108">`provider` 진행 이벤트를 정의할 공급자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-108">`provider` [in] The ID of the provider to define an event on.</span></span>

<span data-ttu-id="e8b89-109">`eventName` 진행 이벤트 이름을 포함 하는 null로 끝나는 와이드 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-109">`eventName` [in] A pointer to a null terminated wide character string that contains the event name.</span></span>

<span data-ttu-id="e8b89-110">`eventID` 진행 정의 되는 이벤트의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-110">`eventID` [in] The ID of the event being defined.</span></span>

<span data-ttu-id="e8b89-111">`keywords` 진행 정의 되는 이벤트의 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-111">`keywords` [in] The keywords of the event being defined.</span></span>

<span data-ttu-id="e8b89-112">`eventVersion` 진행 정의 되는 이벤트의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-112">`eventVersion` [in] The version of the event being defined.</span></span>

<span data-ttu-id="e8b89-113">`level` 진행 정의 되는 이벤트의 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-113">`level` [in] The level of the event being defined.</span></span>

<span data-ttu-id="e8b89-114">`opcode` 진행 정의 되는 이벤트의 opcode입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-114">`opcode` [in] The opcode of the event being defined.</span></span>

<span data-ttu-id="e8b89-115">`needStack` 진행 `BOOL` 이 이벤트가 발생 될 때마다 관리 되는 스택을 수집 해야 하는지 여부를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-115">`needStack` [in] A `BOOL` indicating whether managed stacks should be collected each time this event fires.</span></span>

<span data-ttu-id="e8b89-116">`cParamDescs` 진행 의 매개 변수 개수입니다 `pParamDescs` .</span><span class="sxs-lookup"><span data-stu-id="e8b89-116">`cParamDescs` [in] The count of the number of parameters in `pParamDescs`.</span></span>

<span data-ttu-id="e8b89-117">`pParamDescs` 진행 `COR_PRF_EVENTPIPE_PARAM_DESC` 정의 되는 이벤트에 대 한 매개 변수 형식을 정의 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-117">`pParamDescs` [in] An array of `COR_PRF_EVENTPIPE_PARAM_DESC` defining the parameter types to the event being defined.</span></span>

<span data-ttu-id="e8b89-118">`pEvent` 제한이 함수가 반환 될 때 정의 되는 이벤트의 ID로 채워질 호출자 제공 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e8b89-118">`pEvent` [out] A caller provided pointer that will be filled with the ID of the event being defined when the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8b89-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8b89-119">Requirements</span></span>  

<span data-ttu-id="e8b89-120">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8b89-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="e8b89-121">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8b89-121">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e8b89-122">참조</span><span class="sxs-lookup"><span data-stu-id="e8b89-122">See also</span></span>

- [<span data-ttu-id="e8b89-123">EventPipe 개요</span><span class="sxs-lookup"><span data-stu-id="e8b89-123">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="e8b89-124">잘 알려진 EventProviders</span><span class="sxs-lookup"><span data-stu-id="e8b89-124">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="e8b89-125">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8b89-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e8b89-126">ICorProfilerCallback10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8b89-126">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="e8b89-127">ICorProfilerInfo12 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8b89-127">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="e8b89-128">COR_PRF_EVENTPIPE_PARAM_DESC 구조체</span><span class="sxs-lookup"><span data-stu-id="e8b89-128">COR_PRF_EVENTPIPE_PARAM_DESC Structure</span></span>](cor-prf-eventpipe-param-desc-structure.md)
