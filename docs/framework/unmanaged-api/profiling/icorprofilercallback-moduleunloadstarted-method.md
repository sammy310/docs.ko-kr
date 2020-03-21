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
ms.openlocfilehash: fcfdddbd5316c098754ea7b0d4714b050c64fe55
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175150"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="e67a3-102">ICorProfilerCallback::ModuleUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="e67a3-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="e67a3-103">프로파일러에 모듈이 언로드되고 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e67a3-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e67a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="e67a3-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="e67a3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e67a3-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="e67a3-106">【인】 언로드 중인 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e67a3-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e67a3-107">설명</span><span class="sxs-lookup"><span data-stu-id="e67a3-107">Remarks</span></span>  
 <span data-ttu-id="e67a3-108">메서드가 `moduleId` 반환된 후 정보 요청에 대한 값은 유효하지 않습니다. `ModuleUnloadStarted`</span><span class="sxs-lookup"><span data-stu-id="e67a3-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e67a3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e67a3-109">Requirements</span></span>  
 <span data-ttu-id="e67a3-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e67a3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e67a3-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e67a3-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e67a3-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e67a3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e67a3-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e67a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67a3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e67a3-114">See also</span></span>

- [<span data-ttu-id="e67a3-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e67a3-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e67a3-116">ModuleUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="e67a3-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
