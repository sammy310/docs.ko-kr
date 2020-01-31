---
title: ICorProfilerCallback::ClassLoadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: 5b465216da39e8cf207f0614519720453c384ae9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866587"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="89e1b-102">ICorProfilerCallback::ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="89e1b-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="89e1b-103">클래스를 로드 하는 중임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="89e1b-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e1b-104">구문</span><span class="sxs-lookup"><span data-stu-id="89e1b-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89e1b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89e1b-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="89e1b-106">\[in] 로드 되는 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="89e1b-106">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="89e1b-107">주의</span><span class="sxs-lookup"><span data-stu-id="89e1b-107">Remarks</span></span>  
 <span data-ttu-id="89e1b-108">[ICorProfilerCallback:: ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) 메서드를 호출할 때까지 정보 요청에 `classId` 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89e1b-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e1b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89e1b-109">Requirements</span></span>  
 <span data-ttu-id="89e1b-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89e1b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e1b-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89e1b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89e1b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89e1b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89e1b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e1b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e1b-114">참조</span><span class="sxs-lookup"><span data-stu-id="89e1b-114">See also</span></span>

- [<span data-ttu-id="89e1b-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89e1b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
