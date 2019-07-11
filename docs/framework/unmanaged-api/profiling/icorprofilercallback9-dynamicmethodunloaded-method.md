---
title: ICorProfilerCallback9::DynamicMethodUnloaded 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 680bd351a64632e67432ee03352ee7caa8f4b2d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780382"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="71b17-102">ICorProfilerCallback9::DynamicMethodUnloaded 메서드</span><span class="sxs-lookup"><span data-stu-id="71b17-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="71b17-103">[.NET Framework 4.7.2 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="71b17-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="71b17-104">동적 메서드는 가비지 수집 되 고 이후에 언로드될 때마다 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="71b17-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b17-105">구문</span><span class="sxs-lookup"><span data-stu-id="71b17-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71b17-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71b17-106">Parameters</span></span>  
<span data-ttu-id="71b17-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="71b17-107">[in] `functionId`</span></span>  
<span data-ttu-id="71b17-108">가비지 수집 되 고 언로드된 된 메모리 내 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="71b17-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="71b17-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71b17-109">Requirements</span></span>  
 <span data-ttu-id="71b17-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71b17-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71b17-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71b17-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71b17-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71b17-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71b17-113">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="71b17-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b17-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="71b17-114">See also</span></span>

- [<span data-ttu-id="71b17-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="71b17-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="71b17-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="71b17-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="71b17-117">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71b17-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="71b17-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="71b17-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
