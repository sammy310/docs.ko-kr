---
title: ICorProfilerCallback::ClassUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 752ebc4fcb284fbeb91a1efcda476249632adc5c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790176"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="a3cc8-102">ICorProfilerCallback::ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="a3cc8-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="a3cc8-103">클래스가 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3cc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3cc8-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3cc8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3cc8-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="a3cc8-106">\[in]은 언로드될 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3cc8-107">주의</span><span class="sxs-lookup"><span data-stu-id="a3cc8-107">Remarks</span></span>  
 <span data-ttu-id="a3cc8-108">`classId` 값은 `ClassUnloadStarted` 메서드가 반환 된 후 정보 요청에 유효 하지 않습니다 .이는 프로파일러에서이 클래스에 대 한 정보를 가져올 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3cc8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3cc8-109">Requirements</span></span>  
 <span data-ttu-id="a3cc8-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3cc8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3cc8-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3cc8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3cc8-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3cc8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3cc8-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3cc8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3cc8-114">참조</span><span class="sxs-lookup"><span data-stu-id="a3cc8-114">See also</span></span>

- [<span data-ttu-id="a3cc8-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3cc8-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a3cc8-116">ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="a3cc8-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
