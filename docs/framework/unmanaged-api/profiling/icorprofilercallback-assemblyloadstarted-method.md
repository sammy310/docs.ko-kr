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
ms.openlocfilehash: b83be5e79c533e7e5a2468a12a0793d300700428
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866642"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="fcd3b-102">ICorProfilerCallback::AssemblyLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="fcd3b-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="fcd3b-103">어셈블리가 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fcd3b-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd3b-104">구문</span><span class="sxs-lookup"><span data-stu-id="fcd3b-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcd3b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fcd3b-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="fcd3b-106">\[in] 로드 되는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcd3b-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcd3b-107">주의</span><span class="sxs-lookup"><span data-stu-id="fcd3b-107">Remarks</span></span>  
 <span data-ttu-id="fcd3b-108">[ICorProfilerCallback:: AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) 메서드를 호출할 때까지 정보 요청에 `assemblyId` 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcd3b-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd3b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fcd3b-109">Requirements</span></span>  
 <span data-ttu-id="fcd3b-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcd3b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd3b-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fcd3b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fcd3b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcd3b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcd3b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd3b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd3b-114">참조</span><span class="sxs-lookup"><span data-stu-id="fcd3b-114">See also</span></span>

- [<span data-ttu-id="fcd3b-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fcd3b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
