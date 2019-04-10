---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dbe8d4f7050b93ffb34280be6d63367ef294ae8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206592"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="7f6e1-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="7f6e1-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="7f6e1-103">[.NET Framework 4.7 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="7f6e1-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="7f6e1-104">동적 메서드의 JIT 컴파일 완료 될 때마다 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7f6e1-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f6e1-105">구문</span><span class="sxs-lookup"><span data-stu-id="7f6e1-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f6e1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f6e1-106">Parameters</span></span>  
<span data-ttu-id="7f6e1-107">[in]</span><span class="sxs-lookup"><span data-stu-id="7f6e1-107">[in]</span></span> `functionId`  
<span data-ttu-id="7f6e1-108">식별자는 JIT 컴파일 시작 되는 메모리 내 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f6e1-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="7f6e1-109">[in]</span><span class="sxs-lookup"><span data-stu-id="7f6e1-109">[in]</span></span> `hrStatus`   
<span data-ttu-id="7f6e1-110">JIT 컴파일이 성공 했는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7f6e1-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="7f6e1-111">[in]</span><span class="sxs-lookup"><span data-stu-id="7f6e1-111">[in]</span></span> `fIsSafeToBlock`   
`true` <span data-ttu-id="7f6e1-112">차단 호출 스레드가이 콜백에서; 반환 될 때까지 대기할 런타임 시를 나타내려면 `false` 는 차단 영향을 주지 것입니다 런타임의 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f6e1-112">to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="7f6e1-113">설명</span><span class="sxs-lookup"><span data-stu-id="7f6e1-113">Remarks</span></span>  

<span data-ttu-id="7f6e1-114">이 콜백은 동적 메서드의 JIT 컴파일 완료 될 때마다 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f6e1-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="7f6e1-115">다양 한 IL 스텁 및 LCG 메서드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f6e1-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="7f6e1-116">목표 컴파일된 메서드를 사용자 식별에 충분 한 정보를 사용 하 여 프로파일러 기록기를 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f6e1-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> `functionId` <span data-ttu-id="7f6e1-117">동적 메서드는 메타 데이터가 없는 때문에 해당 메타 데이터 토큰을 확인할 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f6e1-117">values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f6e1-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f6e1-118">Requirements</span></span>  
 <span data-ttu-id="7f6e1-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f6e1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f6e1-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7f6e1-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7f6e1-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f6e1-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7f6e1-122">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="7f6e1-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7f6e1-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="7f6e1-123">See also</span></span>

- [<span data-ttu-id="7f6e1-124">DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="7f6e1-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="7f6e1-125">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f6e1-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
