---
title: ICorProfilerCallback::ModuleLoadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bc4b1a58bba592cfff408f034fb19c0c27616c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480548"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="ef2e9-102">ICorProfilerCallback::ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="ef2e9-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="ef2e9-103">모듈 로드 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e9-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef2e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef2e9-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef2e9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef2e9-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ef2e9-106">[in] 로드 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e9-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef2e9-107">설명</span><span class="sxs-lookup"><span data-stu-id="ef2e9-107">Remarks</span></span>  
 <span data-ttu-id="ef2e9-108">값 `moduleId` 될 때까지 정보 요청에 대해 올바르지 않습니다 합니다 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef2e9-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef2e9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef2e9-109">Requirements</span></span>  
 <span data-ttu-id="ef2e9-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ef2e9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef2e9-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef2e9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef2e9-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef2e9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef2e9-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef2e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2e9-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="ef2e9-114">See also</span></span>
- [<span data-ttu-id="ef2e9-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef2e9-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
