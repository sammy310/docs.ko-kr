---
title: ICorProfilerCallback::ModuleUnloadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
ms.openlocfilehash: fd35f47c004d1ffb235cefe1cd2a1eb2c1fffaef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503317"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="45669-102">ICorProfilerCallback::ModuleUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="45669-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="45669-103">모듈의 언로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="45669-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45669-104">구문</span><span class="sxs-lookup"><span data-stu-id="45669-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45669-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="45669-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="45669-106">진행 언로드된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="45669-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="45669-107">진행 모듈이 성공적으로 언로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="45669-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45669-108">설명</span><span class="sxs-lookup"><span data-stu-id="45669-108">Remarks</span></span>  
 <span data-ttu-id="45669-109">`moduleId` [ICorProfilerCallback:: ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) 메서드가 반환 된 후에는 값이 정보 요청에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45669-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="45669-110">클래스를 언로드하는 일부 부분은 콜백 후에도 계속 될 수 있습니다 `ModuleUnloadFinished` .</span><span class="sxs-lookup"><span data-stu-id="45669-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="45669-111">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45669-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="45669-112">그러나의 성공 HRESULT는 `hrStatus` 모듈 언로드의 첫 번째 부분만 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45669-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45669-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45669-113">Requirements</span></span>  
 <span data-ttu-id="45669-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45669-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45669-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45669-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45669-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45669-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45669-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45669-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45669-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45669-118">See also</span></span>

- [<span data-ttu-id="45669-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45669-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
