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
ms.openlocfilehash: 6fbd009b5785c5dc78df81e4411fbdf8e8eadf71
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730336"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="dc54c-102">ICorProfilerCallback::ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="dc54c-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>

<span data-ttu-id="dc54c-103">모듈이 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="dc54c-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc54c-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc54c-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc54c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc54c-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="dc54c-106">진행 로드 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc54c-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc54c-107">설명</span><span class="sxs-lookup"><span data-stu-id="dc54c-107">Remarks</span></span>  

 <span data-ttu-id="dc54c-108">`moduleId` [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 메서드가 호출 될 때까지 정보 요청에 대 한 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc54c-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc54c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc54c-109">Requirements</span></span>  

 <span data-ttu-id="dc54c-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc54c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc54c-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dc54c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dc54c-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc54c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc54c-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc54c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc54c-114">참조</span><span class="sxs-lookup"><span data-stu-id="dc54c-114">See also</span></span>

- [<span data-ttu-id="dc54c-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc54c-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
