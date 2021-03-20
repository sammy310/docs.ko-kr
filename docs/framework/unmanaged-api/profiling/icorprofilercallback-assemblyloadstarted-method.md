---
description: '자세히 알아보기: ICorProfilerCallback:: AssemblyLoadStarted 메서드'
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
ms.openlocfilehash: 19737fc284d49c3690f66e4881450ca5803622e3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760606"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="2d7f4-103">ICorProfilerCallback::AssemblyLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="2d7f4-103">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>

<span data-ttu-id="2d7f4-104">어셈블리가 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2d7f4-104">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d7f4-105">구문</span><span class="sxs-lookup"><span data-stu-id="2d7f4-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d7f4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2d7f4-106">Parameters</span></span>

<span data-ttu-id="2d7f4-107">`assemblyId` 진행 로드 되는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d7f4-107">`assemblyId` [in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d7f4-108">설명</span><span class="sxs-lookup"><span data-stu-id="2d7f4-108">Remarks</span></span>  

 <span data-ttu-id="2d7f4-109">`assemblyId` [ICorProfilerCallback:: AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) 메서드를 호출할 때까지 정보 요청에 대 한 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d7f4-109">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d7f4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d7f4-110">Requirements</span></span>  

 <span data-ttu-id="2d7f4-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d7f4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d7f4-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d7f4-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d7f4-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d7f4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d7f4-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d7f4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d7f4-115">참조</span><span class="sxs-lookup"><span data-stu-id="2d7f4-115">See also</span></span>

- [<span data-ttu-id="2d7f4-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2d7f4-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
