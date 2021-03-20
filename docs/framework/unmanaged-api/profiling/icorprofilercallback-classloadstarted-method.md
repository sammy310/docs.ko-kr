---
description: '자세히 알아보기: ICorProfilerCallback:: ClassLoadStarted 메서드'
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
ms.openlocfilehash: 4950f1d806efb304a860fa6fce18f8655bdc0976
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759253"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="cbeb5-103">ICorProfilerCallback::ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="cbeb5-103">ICorProfilerCallback::ClassLoadStarted Method</span></span>

<span data-ttu-id="cbeb5-104">클래스를 로드 하는 중임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cbeb5-104">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbeb5-105">구문</span><span class="sxs-lookup"><span data-stu-id="cbeb5-105">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbeb5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cbeb5-106">Parameters</span></span>

<span data-ttu-id="cbeb5-107">`classId` 진행 로드 되는 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbeb5-107">`classId` [in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="cbeb5-108">설명</span><span class="sxs-lookup"><span data-stu-id="cbeb5-108">Remarks</span></span>  

 <span data-ttu-id="cbeb5-109">`classId` [ICorProfilerCallback:: ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) 메서드가 호출 될 때까지 정보 요청에 대 한 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbeb5-109">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbeb5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cbeb5-110">Requirements</span></span>  

 <span data-ttu-id="cbeb5-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbeb5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbeb5-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cbeb5-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cbeb5-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbeb5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbeb5-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbeb5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbeb5-115">참조</span><span class="sxs-lookup"><span data-stu-id="cbeb5-115">See also</span></span>

- [<span data-ttu-id="cbeb5-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cbeb5-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
