---
description: '자세히 알아보기: ICorProfilerCallback7:: Moduleinmemory기호 향상 날짜 메서드'
title: 'ICorProfilerCallback7:: Moduleinmemory기호 및 날짜 메서드'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: fa6056beb5685ca9ce9545efea567ca0df6029ce
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759861"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="4cb5e-103">ICorProfilerCallback7:: Moduleinmemory기호 및 날짜 메서드</span><span class="sxs-lookup"><span data-stu-id="4cb5e-103">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>

<span data-ttu-id="4cb5e-104">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="4cb5e-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="4cb5e-105">메모리 내 모듈과 연관 된 기호 스트림이 업데이트 될 때마다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4cb5e-105">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb5e-106">구문</span><span class="sxs-lookup"><span data-stu-id="4cb5e-106">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cb5e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4cb5e-107">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="4cb5e-108">진행 기호 스트림이 업데이트 되는 메모리 내 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4cb5e-108">[in] The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cb5e-109">설명</span><span class="sxs-lookup"><span data-stu-id="4cb5e-109">Remarks</span></span>  

 <span data-ttu-id="4cb5e-110">이 콜백은 [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드를 호출할 때 [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) 이벤트 마스크 플래그를 설정 하 여 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cb5e-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4cb5e-111">이 이벤트는 현재 api를 통해 암시적으로 만들어지거나 수정 된 기호에 대해 발생 하지 않습니다 <xref:System.Reflection.Emit> .</span><span class="sxs-lookup"><span data-stu-id="4cb5e-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="4cb5e-112">어셈블리에 대 한 기호를 지정 하기 위해 인수를 포함 하는 관리 되는 메서드의 오버 로드 중 하나를 호출 하는 즉시 기호가 제공 되는 경우에도 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> `rawSymbolStore` 런타임은 [moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md) 콜백이 발생 했을 때까지 기호 데이터를 모듈에 실제로 연결 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cb5e-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="4cb5e-113">이 이벤트는 나중에 이러한 모듈의 기호를 수집할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cb5e-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb5e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cb5e-114">Requirements</span></span>  

 <span data-ttu-id="4cb5e-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cb5e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb5e-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4cb5e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4cb5e-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cb5e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cb5e-118">**.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb5e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb5e-119">참조</span><span class="sxs-lookup"><span data-stu-id="4cb5e-119">See also</span></span>

- [<span data-ttu-id="4cb5e-120">ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="4cb5e-120">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="4cb5e-121">SetEventMask2 메서드</span><span class="sxs-lookup"><span data-stu-id="4cb5e-121">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="4cb5e-122">ICorProfilerCallback7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cb5e-122">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)
