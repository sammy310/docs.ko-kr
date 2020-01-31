---
title: ICorProfilerCallback::AssemblyUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: 0a677e33950f178b916a5e9e9cbb7bd918c1349b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866613"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="f9a48-102">ICorProfilerCallback::AssemblyUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="f9a48-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="f9a48-103">어셈블리가 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f9a48-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a48-104">구문</span><span class="sxs-lookup"><span data-stu-id="f9a48-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9a48-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9a48-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="f9a48-106">\[in]은 언로드되고 있는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a48-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9a48-107">주의</span><span class="sxs-lookup"><span data-stu-id="f9a48-107">Remarks</span></span>  
 <span data-ttu-id="f9a48-108">`assemblyId` 값은 `AssemblyUnloadStarted` 메서드가 반환 된 후 정보 요청에 유효 하지 않습니다 .이는 프로파일러에서이 어셈블리에 대 한 정보를 가져올 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="f9a48-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9a48-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9a48-109">Requirements</span></span>  
 <span data-ttu-id="f9a48-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9a48-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9a48-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f9a48-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f9a48-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9a48-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9a48-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9a48-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a48-114">참조</span><span class="sxs-lookup"><span data-stu-id="f9a48-114">See also</span></span>

- [<span data-ttu-id="f9a48-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f9a48-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f9a48-116">AssemblyUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="f9a48-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
