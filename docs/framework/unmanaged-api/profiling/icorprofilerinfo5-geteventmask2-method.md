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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8ebddf9a16b2eddbbc58342f68b517064e8d794
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214639"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="5db17-102">ICorProfilerInfo5::GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="5db17-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="5db17-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="5db17-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="5db17-104">프로파일러가 CLR(공용 언어 런타임)에서 알림을 받으려는 현재 이벤트 범주를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5db17-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="5db17-105">제공 하지 않는 기능을 제공 합니다 [icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5db17-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db17-106">구문</span><span class="sxs-lookup"><span data-stu-id="5db17-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5db17-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5db17-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="5db17-108">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5db17-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="5db17-109">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5db17-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="5db17-110">설명 하는 비트를 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5db17-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="5db17-111">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5db17-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="5db17-112">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5db17-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="5db17-113">설명 하는 비트를 [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5db17-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5db17-114">설명</span><span class="sxs-lookup"><span data-stu-id="5db17-114">Remarks</span></span>  
 <span data-ttu-id="5db17-115">`GetEventMask2` 메서드를 사용하여 프로파일러가 구독한 콜백을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5db17-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="5db17-116">논리 OR를 수행 하는 일반적으로 `pdwEventsLow` 하 고 `pdwEventsHigh` 값과 새 비트를 설정 하 고 호출 하려는 합니다 [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5db17-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="5db17-117">이 메서드는 권장 되는 대신 합니다 [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5db17-117">This method is the recommended alternative to the [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5db17-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5db17-118">Requirements</span></span>  
 <span data-ttu-id="5db17-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5db17-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5db17-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5db17-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5db17-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5db17-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5db17-122">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="5db17-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5db17-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="5db17-123">See also</span></span>

- [<span data-ttu-id="5db17-124">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5db17-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="5db17-125">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="5db17-125">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
