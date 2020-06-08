---
title: ICorProfilerCallback::FunctionUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: 320aaf074452fd02cd8ee8e80194a4c35b831eb4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503382"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="18ae7-102">ICorProfilerCallback::FunctionUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="18ae7-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="18ae7-103">런타임이 함수 언로드를 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="18ae7-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18ae7-104">구문</span><span class="sxs-lookup"><span data-stu-id="18ae7-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="18ae7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18ae7-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="18ae7-106">\[in] 언로드되고 있는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="18ae7-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="18ae7-107">설명</span><span class="sxs-lookup"><span data-stu-id="18ae7-107">Remarks</span></span>  
 <span data-ttu-id="18ae7-108">`functionId`이 메서드가 호출자에 반환 된 후에는 매개 변수 값이 더 이상 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18ae7-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18ae7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18ae7-109">Requirements</span></span>  
 <span data-ttu-id="18ae7-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18ae7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18ae7-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18ae7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="18ae7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18ae7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18ae7-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18ae7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ae7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18ae7-114">See also</span></span>

- [<span data-ttu-id="18ae7-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18ae7-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
