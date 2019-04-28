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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0707351d28ef75083b7bfb6ded38bc2a8460131
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597585"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="8865b-102">ICorProfilerCallback::ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="8865b-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="8865b-103">클래스를 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8865b-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8865b-104">구문</span><span class="sxs-lookup"><span data-stu-id="8865b-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8865b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8865b-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="8865b-106">[in] 언로드되고는 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="8865b-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8865b-107">설명</span><span class="sxs-lookup"><span data-stu-id="8865b-107">Remarks</span></span>  
 <span data-ttu-id="8865b-108">변수의 `classId` 후 정보 요청에 적합 하지 않습니다는 `ClassUnloadStarted` 메서드가 반환 되는-프로파일러의이 클래스에 대 한 정보를 얻을 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="8865b-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8865b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8865b-109">Requirements</span></span>  
 <span data-ttu-id="8865b-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8865b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8865b-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8865b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8865b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8865b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8865b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8865b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8865b-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="8865b-114">See also</span></span>

- [<span data-ttu-id="8865b-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8865b-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8865b-116">ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="8865b-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
