---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4b8bffeb71497a7dd8e2ed25b833f9216d8017e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142248"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="d1ee9-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="d1ee9-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="d1ee9-103">[.NET Framework 4.7 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="d1ee9-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="d1ee9-104">동적 메서드의 JIT 컴파일을 시작한 때마다 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1ee9-105">구문</span><span class="sxs-lookup"><span data-stu-id="d1ee9-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1ee9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1ee9-106">Parameters</span></span>  
<span data-ttu-id="d1ee9-107">[in]</span><span class="sxs-lookup"><span data-stu-id="d1ee9-107">[in]</span></span> `functionId`  
<span data-ttu-id="d1ee9-108">식별자는 JIT 컴파일 시작 되는 메모리 내 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="d1ee9-109">[in]</span><span class="sxs-lookup"><span data-stu-id="d1ee9-109">[in]</span></span> `fIsSafeToBlock`   
`true` <span data-ttu-id="d1ee9-110">차단 호출 스레드가이 콜백에서; 반환 될 때까지 대기할 런타임 시를 나타내려면 `false` 는 차단 영향을 주지 것입니다 런타임의 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-110">to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="d1ee9-111">[in]</span><span class="sxs-lookup"><span data-stu-id="d1ee9-111">[in]</span></span> `pILHeader`    
<span data-ttu-id="d1ee9-112">메서드의 IL 헤더의 첫 번째 바이트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="d1ee9-113">[in]</span><span class="sxs-lookup"><span data-stu-id="d1ee9-113">[in]</span></span> `cbILHeader`    
<span data-ttu-id="d1ee9-114">IL 헤더의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="d1ee9-115">설명</span><span class="sxs-lookup"><span data-stu-id="d1ee9-115">Remarks</span></span>  

<span data-ttu-id="d1ee9-116">이 콜백은 동적 메서드를 JIT 컴파일할 때마다 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="d1ee9-117">다양 한 IL 스텁 및 LCG 메서드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="d1ee9-118">목표 컴파일된 메서드를 사용자 식별에 충분 한 정보를 사용 하 여 프로파일러 기록기를 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> `functionId` <span data-ttu-id="d1ee9-119">동적 메서드는 메타 데이터가 없는 때문에 해당 메타 데이터 토큰을 확인할 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-119">values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="d1ee9-120">`pILHeader` 포인터가 유효 콜백 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="d1ee9-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1ee9-121">Requirements</span></span>  
 <span data-ttu-id="d1ee9-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1ee9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1ee9-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d1ee9-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d1ee9-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1ee9-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d1ee9-125">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d1ee9-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d1ee9-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="d1ee9-126">See also</span></span>

- [<span data-ttu-id="d1ee9-127">DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="d1ee9-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="d1ee9-128">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1ee9-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
