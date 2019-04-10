---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12414064bf0651eab443951bde2a50dcff7b2291
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226976"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="07947-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span><span class="sxs-lookup"><span data-stu-id="07947-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="07947-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="07947-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="07947-104">메모리 내 모듈과 연관 된 기호 스트림이 업데이트 될 때마다 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="07947-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07947-105">구문</span><span class="sxs-lookup"><span data-stu-id="07947-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07947-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07947-106">Parameters</span></span>  
 <span data-ttu-id="07947-107">[in]</span><span class="sxs-lookup"><span data-stu-id="07947-107">[in]</span></span> `moduleId`  
 <span data-ttu-id="07947-108">해당 기호 스트림이 업데이트는 메모리 내 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="07947-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07947-109">설명</span><span class="sxs-lookup"><span data-stu-id="07947-109">Remarks</span></span>  
 <span data-ttu-id="07947-110">이 콜백을 설정 하 여 제어 합니다 [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) 이벤트 마스크 플래그를 호출할 때 합니다 [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="07947-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07947-111">이 이벤트는 암시적으로 생성 되거나를 통해 수정 기호에 대 한 현재 발생 하지 <xref:System.Reflection.Emit> Api.</span><span class="sxs-lookup"><span data-stu-id="07947-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="07947-112">도 때 기호에에서 제공 된 사전 관리 되는 오버 로드 중 하나를 호출 하 <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> 포함 하는 메서드를 `rawSymbolStore` 런타임 어셈블리에 대 한 기호를 지정 하는 인수 기호 데이터 모듈을 사용 하 여 실제로 연결 하지 않을 수 있습니다 될 때까지 후 합니다 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="07947-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="07947-113">이 이벤트는 이러한 모듈에 대 한 기호를 수집 하는 이후 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07947-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07947-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07947-114">Requirements</span></span>  
 <span data-ttu-id="07947-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="07947-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07947-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07947-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07947-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07947-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="07947-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="07947-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="07947-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="07947-119">See also</span></span>

- [<span data-ttu-id="07947-120">ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="07947-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="07947-121">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="07947-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="07947-122">ICorProfilerCallback7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07947-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
