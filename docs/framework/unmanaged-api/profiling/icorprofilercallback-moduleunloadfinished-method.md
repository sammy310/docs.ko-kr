---
title: ICorProfilerCallback::ModuleUnloadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6462fe44459228a377f4e583a8a5a1cd93d939bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480366"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="daa52-102">ICorProfilerCallback::ModuleUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="daa52-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="daa52-103">모듈 언로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="daa52-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daa52-104">구문</span><span class="sxs-lookup"><span data-stu-id="daa52-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daa52-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="daa52-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="daa52-106">[in] 로드 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="daa52-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="daa52-107">[in] 모듈 로드 되었는지 여부를 하지 성공적으로 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="daa52-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daa52-108">설명</span><span class="sxs-lookup"><span data-stu-id="daa52-108">Remarks</span></span>  
 <span data-ttu-id="daa52-109">값 `moduleId` 후 정보 요청에 대해 올바르지 않습니다 합니다 [icorprofilercallback:: Moduleunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) 메서드 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="daa52-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="daa52-110">일부 클래스를 언로드 후 계속 사용할 수는 `ModuleUnloadFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="daa52-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="daa52-111">오류 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="daa52-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="daa52-112">그러나 성공 HRESULT에서 `hrStatus` 모듈 언로드에 대 한 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="daa52-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daa52-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="daa52-113">Requirements</span></span>  
 <span data-ttu-id="daa52-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="daa52-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daa52-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="daa52-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="daa52-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daa52-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daa52-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daa52-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daa52-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="daa52-118">See also</span></span>
- [<span data-ttu-id="daa52-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daa52-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
