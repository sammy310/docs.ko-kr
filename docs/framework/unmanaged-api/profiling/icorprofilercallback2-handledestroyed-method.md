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
ms.openlocfilehash: d7a4f7d08e6d8698dbb58c4c2d111a47d0ccc8db
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499781"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="2557c-102">ICorProfilerCallback2::HandleDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="2557c-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="2557c-103">가비지 수집 핸들이 소멸 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2557c-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2557c-104">구문</span><span class="sxs-lookup"><span data-stu-id="2557c-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2557c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2557c-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="2557c-106">진행 가비지 컬렉션에 대 한 핸들의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2557c-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2557c-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2557c-107">Requirements</span></span>  
 <span data-ttu-id="2557c-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2557c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2557c-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2557c-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2557c-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2557c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2557c-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2557c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2557c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2557c-112">See also</span></span>

- [<span data-ttu-id="2557c-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2557c-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2557c-114">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2557c-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
