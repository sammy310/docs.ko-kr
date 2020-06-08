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
ms.openlocfilehash: 9a9fdc80c8f63dd5b004953266a5d7399655bc71
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500366"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="a8472-102">ICorProfilerCallback::ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="a8472-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="a8472-103">클래스를 로드 하는 중임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a8472-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8472-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8472-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8472-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8472-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="a8472-106">\[in] 로드 되는 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8472-106">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8472-107">설명</span><span class="sxs-lookup"><span data-stu-id="a8472-107">Remarks</span></span>  
 <span data-ttu-id="a8472-108">`classId` [ICorProfilerCallback:: ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) 메서드가 호출 될 때까지 정보 요청에 대 한 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8472-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8472-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8472-109">Requirements</span></span>  
 <span data-ttu-id="a8472-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8472-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8472-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8472-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8472-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8472-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8472-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8472-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8472-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8472-114">See also</span></span>

- [<span data-ttu-id="a8472-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8472-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
