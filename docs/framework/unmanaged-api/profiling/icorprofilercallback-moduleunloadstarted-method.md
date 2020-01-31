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
ms.openlocfilehash: 7e43f58f619aaa63fa2294dd3e989026dcdfc604
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866132"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="9efb1-102">ICorProfilerCallback::ModuleUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="9efb1-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="9efb1-103">모듈이 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9efb1-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9efb1-104">구문</span><span class="sxs-lookup"><span data-stu-id="9efb1-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="9efb1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9efb1-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="9efb1-106">진행 언로드될 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9efb1-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9efb1-107">주의</span><span class="sxs-lookup"><span data-stu-id="9efb1-107">Remarks</span></span>  
 <span data-ttu-id="9efb1-108">`moduleId` 값은 `ModuleUnloadStarted` 메서드가 반환 된 후 정보 요청에 대해 유효 하지 않습니다 .이는이 모듈에 대 한 정보를 가져올 수 있는 프로파일러의 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="9efb1-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9efb1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9efb1-109">Requirements</span></span>  
 <span data-ttu-id="9efb1-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9efb1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9efb1-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9efb1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9efb1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9efb1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9efb1-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9efb1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efb1-114">참조</span><span class="sxs-lookup"><span data-stu-id="9efb1-114">See also</span></span>

- [<span data-ttu-id="9efb1-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9efb1-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9efb1-116">ModuleUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="9efb1-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
