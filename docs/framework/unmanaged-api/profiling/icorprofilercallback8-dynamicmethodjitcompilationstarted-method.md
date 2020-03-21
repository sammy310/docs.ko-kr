---
title: ICorProfilerCallback8::DynamicMethodJIT컴파일 시작 방법
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177048"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="66d96-102">ICorProfilerCallback8::DynamicMethodJIT컴파일 시작 방법</span><span class="sxs-lookup"><span data-stu-id="66d96-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="66d96-103">[.NET 프레임워크 4.7 이후 버전에서 지원]</span><span class="sxs-lookup"><span data-stu-id="66d96-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="66d96-104">동적 메서드의 JIT 컴파일이 시작될 때마다 프로파일러에 이를 고지합니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d96-105">구문</span><span class="sxs-lookup"><span data-stu-id="66d96-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66d96-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66d96-106">Parameters</span></span>  
<span data-ttu-id="66d96-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="66d96-107">[in] `functionId`</span></span>  
<span data-ttu-id="66d96-108">JIT 컴파일이 시작되는 메모리 내 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="66d96-109">【인】 `fIsSafeToBlock` 차단으로 인해 런타임이 호출 스레드가 이 콜백에서 반환될 때까지 기다릴 수 있음을 
 `true` 나타냅니다. `false` 을 사용하여 차단이 런타임 작업에 영향을 미치지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="66d96-110">【인】 `pILHeader` 메서드의 IL 헤더의 첫 번째 바이트에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="66d96-111">【인】 `cbILHeader` IL 헤더의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="66d96-112">설명</span><span class="sxs-lookup"><span data-stu-id="66d96-112">Remarks</span></span>  

<span data-ttu-id="66d96-113">이 콜백은 동적 메서드가 JIT 컴파일될 때마다 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="66d96-114">여기에는 다양한 IL 스텁 및 LCG 방법이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="66d96-115">그 목표는 프로파일러 작성기에 컴파일된 메서드를 사용자에게 식별할 수 있는 충분한 정보를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="66d96-116">`functionId`동적 메서드에는 메타데이터가 없기 때문에 메타데이터 토큰으로 해결하는 데 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="66d96-117">포인터는 `pILHeader` 콜백 중에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="66d96-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="66d96-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66d96-118">Requirements</span></span>  
 <span data-ttu-id="66d96-119">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66d96-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d96-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="66d96-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="66d96-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66d96-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66d96-122">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="66d96-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d96-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66d96-123">See also</span></span>

- [<span data-ttu-id="66d96-124">DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="66d96-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="66d96-125">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66d96-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
