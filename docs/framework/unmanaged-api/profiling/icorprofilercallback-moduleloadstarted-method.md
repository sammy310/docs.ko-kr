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
ms.openlocfilehash: 3503aa1eb86246365e31f52313893ad8713f5748
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153688"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="0c076-102">ICorProfilerCallback::ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="0c076-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="0c076-103">모듈 로드 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0c076-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c076-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c076-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c076-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c076-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="0c076-106">[in] 로드 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c076-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c076-107">설명</span><span class="sxs-lookup"><span data-stu-id="0c076-107">Remarks</span></span>  
 <span data-ttu-id="0c076-108">값 `moduleId` 될 때까지 정보 요청에 대해 올바르지 않습니다 합니다 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c076-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c076-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c076-109">Requirements</span></span>  
 <span data-ttu-id="0c076-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c076-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c076-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c076-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c076-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c076-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0c076-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="0c076-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c076-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c076-114">See also</span></span>

- [<span data-ttu-id="0c076-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c076-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
