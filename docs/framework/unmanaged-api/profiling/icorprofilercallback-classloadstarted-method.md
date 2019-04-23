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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db7a033944272756a739dec39d4df11fde1d48b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178609"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="b2bfd-102">ICorProfilerCallback::ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="b2bfd-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="b2bfd-103">클래스 로드 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b2bfd-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2bfd-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2bfd-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2bfd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2bfd-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="b2bfd-106">[in] 로드 되는 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2bfd-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2bfd-107">설명</span><span class="sxs-lookup"><span data-stu-id="b2bfd-107">Remarks</span></span>  
 <span data-ttu-id="b2bfd-108">값 `classId` 될 때까지 정보 요청에 대해 올바르지 않습니다 합니다 [icorprofilercallback:: Classloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2bfd-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2bfd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2bfd-109">Requirements</span></span>  
 <span data-ttu-id="b2bfd-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b2bfd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2bfd-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2bfd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2bfd-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2bfd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2bfd-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2bfd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bfd-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2bfd-114">See also</span></span>

- [<span data-ttu-id="b2bfd-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2bfd-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
