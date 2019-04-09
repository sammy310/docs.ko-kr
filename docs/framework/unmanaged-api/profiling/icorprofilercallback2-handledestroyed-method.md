---
title: ICorProfilerCallback2::HandleDestroyed 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc6b086b444a769afbf01369b50c69e242a21050
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090487"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="58e65-102">ICorProfilerCallback2::HandleDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="58e65-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="58e65-103">가비지 컬렉션 핸들을 소멸 된 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="58e65-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e65-104">구문</span><span class="sxs-lookup"><span data-stu-id="58e65-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58e65-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58e65-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="58e65-106">[in] ID는 가비지 수집에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="58e65-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58e65-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58e65-107">Requirements</span></span>  
 <span data-ttu-id="58e65-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58e65-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58e65-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58e65-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58e65-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58e65-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="58e65-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="58e65-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="58e65-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="58e65-112">See also</span></span>

- [<span data-ttu-id="58e65-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58e65-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="58e65-114">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58e65-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
