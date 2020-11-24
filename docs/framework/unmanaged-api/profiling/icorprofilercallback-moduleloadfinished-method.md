---
title: ICorProfilerCallback::ModuleLoadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 5a29507ca56cac4ab800845e3a88706dc7a25379
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683994"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="15ce1-102">ICorProfilerCallback::ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="15ce1-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>

<span data-ttu-id="15ce1-103">모듈의 로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="15ce1-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ce1-104">구문</span><span class="sxs-lookup"><span data-stu-id="15ce1-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15ce1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15ce1-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="15ce1-106">진행 로드가 완료 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="15ce1-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="15ce1-107">진행 모듈이 성공적으로 로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="15ce1-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15ce1-108">설명</span><span class="sxs-lookup"><span data-stu-id="15ce1-108">Remarks</span></span>  

 <span data-ttu-id="15ce1-109">`moduleId`메서드를 호출할 때까지 정보 요청에 대 한 값이 유효 하지 않습니다 `ModuleLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="15ce1-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="15ce1-110">모듈 로드의 일부 부분은 콜백 후에도 계속 될 수 있습니다 `ModuleLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="15ce1-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="15ce1-111">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15ce1-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="15ce1-112">그러나의 성공 HRESULT는 `hrStatus` 모듈을 로드 한 첫 번째 부분이 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15ce1-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ce1-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15ce1-113">Requirements</span></span>  

 <span data-ttu-id="15ce1-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15ce1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ce1-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15ce1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15ce1-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15ce1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15ce1-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ce1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ce1-118">참조</span><span class="sxs-lookup"><span data-stu-id="15ce1-118">See also</span></span>

- [<span data-ttu-id="15ce1-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ce1-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="15ce1-120">ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="15ce1-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
