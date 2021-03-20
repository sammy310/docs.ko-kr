---
description: ICorProfilerCallback8::D ynamicMethodJITCompilationFinished 메서드에 대해 자세히 알아보세요.
title: ICorProfilerCallback8::D ynamicMethodJITCompilationFinished 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: d610024af9959790b37a724c2bdbf4dabc89dd20
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759822"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="02825-103">ICorProfilerCallback8::D ynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="02825-103">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>

<span data-ttu-id="02825-104">[.NET Framework 4.7 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="02825-104">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="02825-105">동적 메서드의 JIT 컴파일이 완료 될 때마다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="02825-105">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02825-106">구문</span><span class="sxs-lookup"><span data-stu-id="02825-106">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02825-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02825-107">Parameters</span></span>  

`functionId`  
<span data-ttu-id="02825-108">진행 JIT 컴파일이 시작 되는 메모리 내 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="02825-108">[in] The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="02825-109">`hrStatus` 진행 JIT 컴파일에 성공 했는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="02825-109">`hrStatus` [in] A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="02825-110">`fIsSafeToBlock` [in] `true` 차단으로 인해 런타임에서 호출 스레드가이 콜백에서 반환 될 때까지 대기 하 게 될 수 있음을 나타내려면이 고, `false` 를 지정 하면 차단이 런타임 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02825-110">`fIsSafeToBlock` [in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="02825-111">설명</span><span class="sxs-lookup"><span data-stu-id="02825-111">Remarks</span></span>  

<span data-ttu-id="02825-112">이 콜백은 동적 메서드의 JIT 컴파일이 완료 될 때마다 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="02825-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="02825-113">여기에는 다양 한 IL 스텁 및 LCG 메서드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02825-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="02825-114">이는 사용자에 게 컴파일된 메서드를 식별 하는 데 충분 한 정보를 제공 하는 프로파일러 작성기를 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="02825-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="02825-115">`functionId` 동적 메서드에 메타 데이터가 없으므로 값을 사용 하 여 메타 데이터 토큰을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02825-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="02825-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02825-116">Requirements</span></span>  

 <span data-ttu-id="02825-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02825-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02825-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02825-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02825-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02825-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02825-120">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="02825-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02825-121">참조</span><span class="sxs-lookup"><span data-stu-id="02825-121">See also</span></span>

- [<span data-ttu-id="02825-122">DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="02825-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="02825-123">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02825-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
