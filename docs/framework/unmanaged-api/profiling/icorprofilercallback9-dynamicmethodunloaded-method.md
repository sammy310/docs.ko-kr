---
description: ICorProfilerCallback9::D ynamicMethodUnloaded 메서드에 대해 자세히 알아보세요.
title: ICorProfilerCallback9::D ynamicMethodUnloaded 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: bc7f95b5101658c93eeb9fcef51e9c0f1bd2f2bd
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760199"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="1ef3b-103">ICorProfilerCallback9::D ynamicMethodUnloaded 메서드</span><span class="sxs-lookup"><span data-stu-id="1ef3b-103">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>

<span data-ttu-id="1ef3b-104">[.NET Framework 4.7.2 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="1ef3b-104">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="1ef3b-105">동적 메서드가 가비지 수집 되 고 이후에 언로드될 때마다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-105">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef3b-106">구문</span><span class="sxs-lookup"><span data-stu-id="1ef3b-106">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ef3b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ef3b-107">Parameters</span></span>  

<span data-ttu-id="1ef3b-108">`functionId` 진행 가비지 수집 및 언로드된 메모리 내 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-108">`functionId` [in] The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ef3b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ef3b-109">Requirements</span></span>  

 <span data-ttu-id="1ef3b-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ef3b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ef3b-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ef3b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ef3b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ef3b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ef3b-113">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1ef3b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef3b-114">참조</span><span class="sxs-lookup"><span data-stu-id="1ef3b-114">See also</span></span>

- [<span data-ttu-id="1ef3b-115">ICorProfilerCallback8 DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="1ef3b-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="1ef3b-116">ICorProfilerCallback8 DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="1ef3b-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="1ef3b-117">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ef3b-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="1ef3b-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="1ef3b-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
