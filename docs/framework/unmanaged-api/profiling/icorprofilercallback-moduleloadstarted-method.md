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
ms.openlocfilehash: 88da5a968bf224dc5b6f45ee5d1d2e75386086f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866158"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="00781-102">ICorProfilerCallback::ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="00781-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="00781-103">모듈이 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="00781-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00781-104">구문</span><span class="sxs-lookup"><span data-stu-id="00781-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00781-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="00781-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="00781-106">진행 로드 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="00781-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00781-107">주의</span><span class="sxs-lookup"><span data-stu-id="00781-107">Remarks</span></span>  
 <span data-ttu-id="00781-108">[ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 메서드를 호출할 때까지 정보 요청에 `moduleId` 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00781-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00781-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00781-109">Requirements</span></span>  
 <span data-ttu-id="00781-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00781-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00781-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="00781-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="00781-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00781-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00781-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00781-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00781-114">참조</span><span class="sxs-lookup"><span data-stu-id="00781-114">See also</span></span>

- [<span data-ttu-id="00781-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00781-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
