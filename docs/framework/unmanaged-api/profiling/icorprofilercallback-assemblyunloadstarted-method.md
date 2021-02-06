---
description: '자세히 알아보기: ICorProfilerCallback:: AssemblyUnloadStarted 메서드'
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
ms.openlocfilehash: e9c72d481df7242f305b5efa6f747866984b31f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657838"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="5bdf1-103">ICorProfilerCallback::AssemblyUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="5bdf1-103">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>

<span data-ttu-id="5bdf1-104">어셈블리가 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-104">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bdf1-105">구문</span><span class="sxs-lookup"><span data-stu-id="5bdf1-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bdf1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bdf1-106">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="5bdf1-107">\[in]은 언로드되고 있는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-107">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="5bdf1-108">설명</span><span class="sxs-lookup"><span data-stu-id="5bdf1-108">Remarks</span></span>  

 <span data-ttu-id="5bdf1-109">메서드가 반환 된 후의 값은 `assemblyId` 정보 요청에 적합 하지 않습니다 .이는 `AssemblyUnloadStarted` 프로파일러에서이 어셈블리에 대 한 정보를 가져올 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-109">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bdf1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bdf1-110">Requirements</span></span>  

 <span data-ttu-id="5bdf1-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bdf1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bdf1-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5bdf1-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5bdf1-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bdf1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bdf1-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bdf1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bdf1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bdf1-115">See also</span></span>

- [<span data-ttu-id="5bdf1-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bdf1-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5bdf1-117">AssemblyUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="5bdf1-117">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
