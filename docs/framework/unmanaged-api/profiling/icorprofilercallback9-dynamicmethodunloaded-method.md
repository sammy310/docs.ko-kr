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
ms.openlocfilehash: 96cdfb79c1573648173305d6ee789aa8db030ff8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211012"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="72203-102">ICorProfilerCallback9::DynamicMethodUnloaded 메서드</span><span class="sxs-lookup"><span data-stu-id="72203-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="72203-103">[.NET Framework 4.7.2 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="72203-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="72203-104">동적 메서드는 가비지 수집 되 고 이후에 언로드될 때마다 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="72203-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72203-105">구문</span><span class="sxs-lookup"><span data-stu-id="72203-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72203-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72203-106">Parameters</span></span>  
<span data-ttu-id="72203-107">[in]</span><span class="sxs-lookup"><span data-stu-id="72203-107">[in]</span></span> `functionId`  
<span data-ttu-id="72203-108">가비지 수집 되 고 언로드된 된 메모리 내 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="72203-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="72203-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72203-109">Requirements</span></span>  
 <span data-ttu-id="72203-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="72203-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72203-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72203-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72203-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72203-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="72203-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="72203-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72203-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="72203-114">See also</span></span>

- [<span data-ttu-id="72203-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span><span class="sxs-lookup"><span data-stu-id="72203-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="72203-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span><span class="sxs-lookup"><span data-stu-id="72203-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="72203-117">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72203-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="72203-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="72203-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
