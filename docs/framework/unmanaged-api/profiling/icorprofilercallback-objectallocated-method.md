---
title: ICorProfilerCallback::ObjectAllocated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: fda234a6a280aeea1f497ad195d6d41efb6aa951
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674346"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="e5cb9-102">ICorProfilerCallback::ObjectAllocated 메서드</span><span class="sxs-lookup"><span data-stu-id="e5cb9-102">ICorProfilerCallback::ObjectAllocated Method</span></span>

<span data-ttu-id="e5cb9-103">힙에 있는 메모리가 개체에 할당 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e5cb9-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5cb9-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5cb9-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5cb9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5cb9-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="e5cb9-106">진행 메모리가 할당 된 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e5cb9-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="e5cb9-107">진행 개체가 인스턴스인 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e5cb9-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5cb9-108">설명</span><span class="sxs-lookup"><span data-stu-id="e5cb9-108">Remarks</span></span>  

 <span data-ttu-id="e5cb9-109">`ObjectedAllocated`스택 또는 관리 되지 않는 메모리의 할당에 대해 메서드가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5cb9-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="e5cb9-110">`classId`매개 변수는 아직 로드 되지 않은 관리 코드의 클래스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5cb9-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="e5cb9-111">프로파일러는 콜백 직후 해당 클래스에 대 한 클래스 로드 콜백을 받게 됩니다 `ObjectAllocated` .</span><span class="sxs-lookup"><span data-stu-id="e5cb9-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5cb9-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5cb9-112">Requirements</span></span>  

 <span data-ttu-id="e5cb9-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5cb9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5cb9-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5cb9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5cb9-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5cb9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5cb9-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5cb9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5cb9-117">참조</span><span class="sxs-lookup"><span data-stu-id="e5cb9-117">See also</span></span>

- [<span data-ttu-id="e5cb9-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5cb9-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e5cb9-119">ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="e5cb9-119">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="e5cb9-120">ClassLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="e5cb9-120">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
