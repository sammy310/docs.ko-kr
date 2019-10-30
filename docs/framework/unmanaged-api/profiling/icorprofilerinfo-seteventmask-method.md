---
title: ICorProfilerInfo::SetEventMask 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
ms.openlocfilehash: b79668130570dc69a580fbf7da4dc122389d9ef0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136692"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="ea9c4-102">ICorProfilerInfo::SetEventMask 메서드</span><span class="sxs-lookup"><span data-stu-id="ea9c4-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="ea9c4-103">프로파일러가 CLR(공용 언어 런타임)에서 알림을 받고 싶은 이벤트 형식을 지정하는 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9c4-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea9c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="ea9c4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea9c4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea9c4-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="ea9c4-106">[in] 이벤트 범주를 지정하는 4바이트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ea9c4-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="ea9c4-107">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9c4-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="ea9c4-108">비트는 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea9c4-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea9c4-109">주의</span><span class="sxs-lookup"><span data-stu-id="ea9c4-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea9c4-110">이 메서드 대신 [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9c4-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="ea9c4-111">`SetEventMask` 메서드는 계속 지원 되지만 [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 는 추가 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9c4-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea9c4-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea9c4-112">Requirements</span></span>  
 <span data-ttu-id="ea9c4-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea9c4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea9c4-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea9c4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea9c4-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea9c4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea9c4-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea9c4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea9c4-117">참조</span><span class="sxs-lookup"><span data-stu-id="ea9c4-117">See also</span></span>

- [<span data-ttu-id="ea9c4-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea9c4-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="ea9c4-119">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="ea9c4-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
