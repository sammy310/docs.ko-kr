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
ms.openlocfilehash: a04f72fff9a88c8689821131b08b35500c23b3d9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503356"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="0825d-102">ICorProfilerCallback::ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="0825d-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="0825d-103">모듈이 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0825d-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0825d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0825d-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0825d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0825d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="0825d-106">진행 로드 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0825d-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0825d-107">설명</span><span class="sxs-lookup"><span data-stu-id="0825d-107">Remarks</span></span>  
 <span data-ttu-id="0825d-108">`moduleId` [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 메서드가 호출 될 때까지 정보 요청에 대 한 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0825d-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0825d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0825d-109">Requirements</span></span>  
 <span data-ttu-id="0825d-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0825d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0825d-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0825d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0825d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0825d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0825d-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0825d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0825d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0825d-114">See also</span></span>

- [<span data-ttu-id="0825d-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0825d-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
