---
title: ICorProfilerCallback::ClassUnloadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d01f3d7485b19c076d9cd3e83aeccbcf5e728f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160708"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="041dc-102">ICorProfilerCallback::ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="041dc-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="041dc-103">클래스 언로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="041dc-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="041dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="041dc-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="041dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="041dc-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="041dc-106">[in] 로드 되지 않은 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="041dc-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="041dc-107">[in] 클래스 로드 되었는지 여부를 하지 성공적으로 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="041dc-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="041dc-108">설명</span><span class="sxs-lookup"><span data-stu-id="041dc-108">Remarks</span></span>  
 <span data-ttu-id="041dc-109">일부 클래스를 언로드 후 계속 사용할 수는 `ClassUnloadFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="041dc-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="041dc-110">오류 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="041dc-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="041dc-111">그러나 성공 HRESULT에서 `hrStatus` 언로드 클래스에 대 한 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="041dc-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="041dc-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="041dc-112">Requirements</span></span>  
 <span data-ttu-id="041dc-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="041dc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="041dc-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="041dc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="041dc-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="041dc-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="041dc-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="041dc-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="041dc-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="041dc-117">See also</span></span>

- [<span data-ttu-id="041dc-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="041dc-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="041dc-119">ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="041dc-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
