---
description: 'ICorProfilerCallback2:: HandleDestroyed 메서드에 대해 자세히 알아보세요.'
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
ms.openlocfilehash: d583a2170efbb4ebe72d7eacdd60af1a089a518f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705584"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="2785c-103">ICorProfilerCallback2::HandleDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="2785c-103">ICorProfilerCallback2::HandleDestroyed Method</span></span>

<span data-ttu-id="2785c-104">가비지 수집 핸들이 소멸 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2785c-104">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2785c-105">구문</span><span class="sxs-lookup"><span data-stu-id="2785c-105">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2785c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2785c-106">Parameters</span></span>  

 `handleId`  
 <span data-ttu-id="2785c-107">진행 가비지 컬렉션에 대 한 핸들의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2785c-107">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2785c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2785c-108">Requirements</span></span>  

 <span data-ttu-id="2785c-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2785c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2785c-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2785c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2785c-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2785c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2785c-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2785c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2785c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2785c-113">See also</span></span>

- [<span data-ttu-id="2785c-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2785c-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2785c-115">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2785c-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
