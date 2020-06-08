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
ms.openlocfilehash: c7ad94bf766e0fcdbff95b0766cf68c2196a2c71
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503337"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="05e3c-102">ICorProfilerCallback::ModuleUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="05e3c-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="05e3c-103">모듈이 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="05e3c-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05e3c-104">구문</span><span class="sxs-lookup"><span data-stu-id="05e3c-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="05e3c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="05e3c-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="05e3c-106">진행 언로드될 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="05e3c-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05e3c-107">설명</span><span class="sxs-lookup"><span data-stu-id="05e3c-107">Remarks</span></span>  
 <span data-ttu-id="05e3c-108">메서드가 반환 된 후의 값은 `moduleId` 정보 요청에 적합 하지 않습니다 `ModuleUnloadStarted` .이 모듈에 대 한 정보를 가져올 수 있는 프로파일러의 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="05e3c-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05e3c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05e3c-109">Requirements</span></span>  
 <span data-ttu-id="05e3c-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05e3c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e3c-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="05e3c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="05e3c-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05e3c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05e3c-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05e3c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e3c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05e3c-114">See also</span></span>

- [<span data-ttu-id="05e3c-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05e3c-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="05e3c-116">ModuleUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="05e3c-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
