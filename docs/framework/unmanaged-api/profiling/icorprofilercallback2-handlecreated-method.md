---
title: ICorProfilerCallback2::HandleCreated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type:
- apiref
ms.openlocfilehash: 0c25a5cad01ef0eb268e90c38bd24d638b6f8cc4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865768"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="c2c0f-102">ICorProfilerCallback2::HandleCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="c2c0f-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="c2c0f-103">가비지 수집 핸들이 생성 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2c0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2c0f-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2c0f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2c0f-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="c2c0f-106">진행 가비지 컬렉션에 대 한 핸들의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="c2c0f-107">진행 가비지 수집 핸들을 만든 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2c0f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2c0f-108">Requirements</span></span>  
 <span data-ttu-id="c2c0f-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2c0f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2c0f-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2c0f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2c0f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2c0f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2c0f-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2c0f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c0f-113">참조</span><span class="sxs-lookup"><span data-stu-id="c2c0f-113">See also</span></span>

- [<span data-ttu-id="c2c0f-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2c0f-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c2c0f-115">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2c0f-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
