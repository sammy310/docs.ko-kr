---
title: ICorProfilerInfo5::GetEventMask2 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: 81509db178b0ab1a524dcc4b00f39264e87a220d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682785"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="a3a0a-102">ICorProfilerInfo5::GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="a3a0a-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>

<span data-ttu-id="a3a0a-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="a3a0a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a3a0a-104">프로파일러가 CLR(공용 언어 런타임)에서 알림을 받으려는 현재 이벤트 범주를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="a3a0a-105">[ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) 메서드에서 제공 하지 않는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a0a-106">구문</span><span class="sxs-lookup"><span data-stu-id="a3a0a-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3a0a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3a0a-107">Parameters</span></span>  

 `pdwEventsLow`  
 <span data-ttu-id="a3a0a-108">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="a3a0a-109">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="a3a0a-110">비트는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="a3a0a-111">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="a3a0a-112">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="a3a0a-113">비트는 [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3a0a-114">설명</span><span class="sxs-lookup"><span data-stu-id="a3a0a-114">Remarks</span></span>  

 <span data-ttu-id="a3a0a-115">`GetEventMask2` 메서드를 사용하여 프로파일러가 구독한 콜백을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="a3a0a-116">일반적으로 `pdwEventsLow` 및 값 및 설정 하려는 새 비트의 논리 OR을 수행한 `pdwEventsHigh` 다음 [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="a3a0a-117">[Geteventmask](icorprofilerinfo-geteventmask-method.md) 메서드 대신이 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-117">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3a0a-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3a0a-118">Requirements</span></span>  

 <span data-ttu-id="a3a0a-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3a0a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3a0a-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3a0a-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3a0a-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3a0a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3a0a-122">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3a0a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a0a-123">참조</span><span class="sxs-lookup"><span data-stu-id="a3a0a-123">See also</span></span>

- [<span data-ttu-id="a3a0a-124">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3a0a-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="a3a0a-125">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="a3a0a-125">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
