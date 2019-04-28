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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a96a2a0d6e4bc48a46850aeaadd17c2669419cef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597454"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="c0859-102">ICorProfilerCallback::AssemblyLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="c0859-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="c0859-103">어셈블리 로드 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c0859-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0859-104">구문</span><span class="sxs-lookup"><span data-stu-id="c0859-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0859-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c0859-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="c0859-106">[in] 로드 되는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0859-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0859-107">설명</span><span class="sxs-lookup"><span data-stu-id="c0859-107">Remarks</span></span>  
 <span data-ttu-id="c0859-108">값 `assemblyId` 될 때까지 정보 요청에 대해 올바르지 않습니다 합니다 [icorprofilercallback:: Assemblyloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0859-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0859-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0859-109">Requirements</span></span>  
 <span data-ttu-id="c0859-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c0859-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0859-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0859-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0859-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0859-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0859-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0859-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0859-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c0859-114">See also</span></span>

- [<span data-ttu-id="c0859-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0859-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
