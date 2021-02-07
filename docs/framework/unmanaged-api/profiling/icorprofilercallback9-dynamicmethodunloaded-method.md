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
ms.openlocfilehash: 243660d3159e3c8c1d052c08e9c7499e7065d301
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753330"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="faede-103">ICorProfilerCallback9::D ynamicMethodUnloaded 메서드</span><span class="sxs-lookup"><span data-stu-id="faede-103">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>

<span data-ttu-id="faede-104">[.NET Framework 4.7.2 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="faede-104">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="faede-105">동적 메서드가 가비지 수집 되 고 이후에 언로드될 때마다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="faede-105">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faede-106">구문</span><span class="sxs-lookup"><span data-stu-id="faede-106">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faede-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="faede-107">Parameters</span></span>  

<span data-ttu-id="faede-108">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="faede-108">[in] `functionId`</span></span>  
<span data-ttu-id="faede-109">가비지 수집 및 언로드된 메모리 내 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="faede-109">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="faede-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="faede-110">Requirements</span></span>  

 <span data-ttu-id="faede-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="faede-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faede-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="faede-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="faede-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faede-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faede-114">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="faede-114">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faede-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="faede-115">See also</span></span>

- [<span data-ttu-id="faede-116">ICorProfilerCallback8 DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="faede-116">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="faede-117">ICorProfilerCallback8 DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="faede-117">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="faede-118">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="faede-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="faede-119">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="faede-119">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
