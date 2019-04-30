---
title: ICorProfilerCallback::ModuleUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb00a56b0d80b78867f70e64c1c9bdf0fc49e1be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041940"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="128d0-102">ICorProfilerCallback::ModuleUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="128d0-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="128d0-103">모듈은 언로드됩니다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="128d0-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="128d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="128d0-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="128d0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="128d0-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="128d0-106">[in] 언로드되고 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="128d0-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="128d0-107">설명</span><span class="sxs-lookup"><span data-stu-id="128d0-107">Remarks</span></span>  
 <span data-ttu-id="128d0-108">변수의 `moduleId` 후 정보 요청에 적합 하지 않습니다는 `ModuleUnloadStarted` 메서드가 반환 되는-프로파일러의이 모듈에 대 한 정보를 얻을 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="128d0-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="128d0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="128d0-109">Requirements</span></span>  
 <span data-ttu-id="128d0-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="128d0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="128d0-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="128d0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="128d0-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="128d0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="128d0-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="128d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="128d0-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="128d0-114">See also</span></span>

- [<span data-ttu-id="128d0-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="128d0-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="128d0-116">ModuleUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="128d0-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
