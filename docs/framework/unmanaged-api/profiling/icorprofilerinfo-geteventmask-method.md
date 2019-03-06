---
title: ICorProfilerInfo::GetEventMask 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1051f42788b3c2a63780f43f5784b063ef23027
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483993"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="814f4-102">ICorProfilerInfo::GetEventMask 메서드</span><span class="sxs-lookup"><span data-stu-id="814f4-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="814f4-103">프로파일러가 CLR(공용 언어 런타임)에서 이벤트 알림을 받으려는 현재 이벤트 범주를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="814f4-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="814f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="814f4-104">Syntax</span></span>  
  
```  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="814f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="814f4-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="814f4-106">[out] 이벤트 범주를 지정하는 4바이트 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="814f4-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="814f4-107">각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="814f4-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="814f4-108">설명 하는 비트를 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="814f4-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="814f4-109">설명</span><span class="sxs-lookup"><span data-stu-id="814f4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="814f4-110">호출 해야 합니다 [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) 이 메서드 대신 메서드.</span><span class="sxs-lookup"><span data-stu-id="814f4-110">You should call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="814f4-111">하지만 합니다 `SetEventMask` 메서드는 계속 지원 될 [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) 추가 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="814f4-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="814f4-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="814f4-112">Requirements</span></span>  
 <span data-ttu-id="814f4-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="814f4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="814f4-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="814f4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="814f4-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="814f4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="814f4-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="814f4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="814f4-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="814f4-117">See also</span></span>
- [<span data-ttu-id="814f4-118">GetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="814f4-118">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="814f4-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="814f4-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
