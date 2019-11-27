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
ms.openlocfilehash: 08fbf49e6944de4934a9fe7a960405ee96a7d8e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445946"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="cdf92-102">ICorProfilerCallback::ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="cdf92-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="cdf92-103">모듈의 로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cdf92-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdf92-104">구문</span><span class="sxs-lookup"><span data-stu-id="cdf92-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdf92-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdf92-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="cdf92-106">진행 로드가 완료 된 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cdf92-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="cdf92-107">진행 모듈이 성공적으로 로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="cdf92-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdf92-108">주의</span><span class="sxs-lookup"><span data-stu-id="cdf92-108">Remarks</span></span>  
 <span data-ttu-id="cdf92-109">`moduleId` 값은 `ModuleLoadFinished` 메서드를 호출할 때까지 정보 요청에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf92-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="cdf92-110">모듈 로드의 일부 부분은 `ModuleLoadFinished` 콜백 후에도 계속 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf92-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="cdf92-111">`hrStatus` 오류 HRESULT는 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cdf92-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="cdf92-112">그러나 `hrStatus`의 성공 HRESULT는 모듈을 로드 한 첫 번째 부분이 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cdf92-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdf92-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdf92-113">Requirements</span></span>  
 <span data-ttu-id="cdf92-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cdf92-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdf92-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cdf92-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cdf92-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdf92-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdf92-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdf92-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdf92-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdf92-118">See also</span></span>

- [<span data-ttu-id="cdf92-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdf92-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cdf92-120">ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="cdf92-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
