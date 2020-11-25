---
title: ICorProfilerCallback::AssemblyLoadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
ms.openlocfilehash: c2fbc0ae8cdeb79b65cbad9a055a8051acf67e50
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700420"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="76e71-102">ICorProfilerCallback::AssemblyLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="76e71-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>

<span data-ttu-id="76e71-103">어셈블리가 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="76e71-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e71-104">구문</span><span class="sxs-lookup"><span data-stu-id="76e71-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76e71-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76e71-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="76e71-106">\[in] 로드 되는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="76e71-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="76e71-107">설명</span><span class="sxs-lookup"><span data-stu-id="76e71-107">Remarks</span></span>  

 <span data-ttu-id="76e71-108">`assemblyId` [ICorProfilerCallback:: AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) 메서드를 호출할 때까지 정보 요청에 대 한 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76e71-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76e71-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76e71-109">Requirements</span></span>  

 <span data-ttu-id="76e71-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76e71-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76e71-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="76e71-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="76e71-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76e71-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76e71-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76e71-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e71-114">참조</span><span class="sxs-lookup"><span data-stu-id="76e71-114">See also</span></span>

- [<span data-ttu-id="76e71-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76e71-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
