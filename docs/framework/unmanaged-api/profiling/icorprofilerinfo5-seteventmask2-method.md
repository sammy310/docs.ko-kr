---
title: ICorProfilerInfo5::SetEventMask2 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 75e2bfc8dfae4d0cd453eba0697d6ee2f0da7133
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733791"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="c096f-102">ICorProfilerInfo5::SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="c096f-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>

<span data-ttu-id="c096f-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="c096f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c096f-104">프로파일러가 CLR(공용 언어 런타임)에서 이벤트 알림을 받을 이벤트 형식을 지정하는 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="c096f-105">[ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드보다 더 많은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c096f-106">구문</span><span class="sxs-lookup"><span data-stu-id="c096f-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c096f-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c096f-107">Parameters</span></span>  

 `dwEventsLow`  
 <span data-ttu-id="c096f-108">[in] 이벤트 범주를 지정하는 4바이트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="c096f-109">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="c096f-110">비트는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="c096f-111">[in] 이벤트 범주를 지정하는 4바이트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="c096f-112">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="c096f-113">비트는 [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c096f-114">설명</span><span class="sxs-lookup"><span data-stu-id="c096f-114">Remarks</span></span>  

 <span data-ttu-id="c096f-115">`SetEventMask2` 메서드를 사용하여 프로파일러가 구독하는 콜백을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="c096f-116">일반적으로 [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) 메서드를 호출 하 여 설정 되는 비트를 확인 하 고, 해당 `pdwEventsLow` 및 값과 설정 하려는 새 비트의 논리 OR을 수행한 `pdwEventsHigh` 다음 메서드를 호출 `SetEventMask2` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-116">Typically, you call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="c096f-117">이 메서드는 [Seteventmask](icorprofilerinfo-seteventmask-method.md) 메서드 대신 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c096f-117">This method is the recommended alternative to the [SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c096f-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c096f-118">Requirements</span></span>  

 <span data-ttu-id="c096f-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c096f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c096f-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c096f-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c096f-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c096f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c096f-122">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c096f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c096f-123">참조</span><span class="sxs-lookup"><span data-stu-id="c096f-123">See also</span></span>

- [<span data-ttu-id="c096f-124">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c096f-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="c096f-125">GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="c096f-125">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
