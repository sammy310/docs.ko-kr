---
description: '자세히 알아보기: ICorProfilerCallback:: Initialize 메서드'
title: ICorProfilerCallback::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: c7138a1a39a1d32c751c205a86c00e6070a236b3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760420"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="3e115-103">ICorProfilerCallback::Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="3e115-103">ICorProfilerCallback::Initialize Method</span></span>

<span data-ttu-id="3e115-104">새 CLR (공용 언어 런타임) 응용 프로그램이 시작 될 때마다 코드 프로파일러를 초기화 하기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e115-104">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e115-105">구문</span><span class="sxs-lookup"><span data-stu-id="3e115-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e115-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e115-106">Parameters</span></span>

<span data-ttu-id="3e115-107">`pICorProfilerInfoUnk`진행 프로파일러가 [ICorProfilerInfo](icorprofilerinfo-interface.md) 인터페이스 포인터를 쿼리해야 하는 [IUnknown](/cpp/atl/iunknown) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3e115-107">`pICorProfilerInfoUnk` [in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="3e115-108">설명</span><span class="sxs-lookup"><span data-stu-id="3e115-108">Remarks</span></span>  

 <span data-ttu-id="3e115-109">`Initialize`이 호출은 변경할 수 없는 콜백을 활성화 (또는 비활성화) 하는 유일한 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="3e115-109">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="3e115-110">호출로 콜백을 사용 하도록 설정한 후 `Initialize` 에는 나중에 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)를 사용 하 여 콜백을 사용 하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e115-110">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="3e115-111">[COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형의 COR_PRF_MONITOR_IMMUTABLE 값은 변경할 수 없는 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e115-111">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e115-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e115-112">Requirements</span></span>  

 <span data-ttu-id="3e115-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e115-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e115-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e115-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e115-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e115-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e115-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e115-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e115-117">참조</span><span class="sxs-lookup"><span data-stu-id="3e115-117">See also</span></span>

- [<span data-ttu-id="3e115-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e115-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3e115-119">Shutdown 메서드</span><span class="sxs-lookup"><span data-stu-id="3e115-119">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
