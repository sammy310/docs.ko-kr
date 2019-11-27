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
ms.openlocfilehash: 55927167f8b61ade4ef479b30b85ad8d82be8025
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445931"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="ebff6-102">ICorProfilerCallback::ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="ebff6-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="ebff6-103">모듈이 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ebff6-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebff6-104">구문</span><span class="sxs-lookup"><span data-stu-id="ebff6-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebff6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ebff6-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ebff6-106">진행 로드 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ebff6-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebff6-107">주의</span><span class="sxs-lookup"><span data-stu-id="ebff6-107">Remarks</span></span>  
 <span data-ttu-id="ebff6-108">[ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 메서드를 호출할 때까지 정보 요청에 `moduleId` 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebff6-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebff6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ebff6-109">Requirements</span></span>  
 <span data-ttu-id="ebff6-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebff6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebff6-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ebff6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ebff6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebff6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebff6-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebff6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebff6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebff6-114">See also</span></span>

- [<span data-ttu-id="ebff6-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebff6-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
