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
ms.openlocfilehash: 66643bbb8dbc914b2e0e48a7f0c87630fe95e5d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445845"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="34fbe-102">ICorProfilerCallback::ObjectAllocated 메서드</span><span class="sxs-lookup"><span data-stu-id="34fbe-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="34fbe-103">힙에 있는 메모리가 개체에 할당 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="34fbe-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34fbe-104">구문</span><span class="sxs-lookup"><span data-stu-id="34fbe-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34fbe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34fbe-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="34fbe-106">진행 메모리가 할당 된 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="34fbe-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="34fbe-107">진행 개체가 인스턴스인 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="34fbe-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34fbe-108">주의</span><span class="sxs-lookup"><span data-stu-id="34fbe-108">Remarks</span></span>  
 <span data-ttu-id="34fbe-109">스택 또는 관리 되지 않는 메모리의 할당에 대해서는 `ObjectedAllocated` 메서드가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34fbe-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="34fbe-110">`classId` 매개 변수는 아직 로드 되지 않은 관리 코드의 클래스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34fbe-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="34fbe-111">프로파일러는 `ObjectAllocated` 콜백 직후 해당 클래스에 대 한 클래스 로드 콜백을 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="34fbe-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34fbe-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34fbe-112">Requirements</span></span>  
 <span data-ttu-id="34fbe-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34fbe-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34fbe-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="34fbe-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="34fbe-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34fbe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34fbe-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34fbe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34fbe-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34fbe-117">See also</span></span>

- [<span data-ttu-id="34fbe-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34fbe-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="34fbe-119">ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="34fbe-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="34fbe-120">ClassLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="34fbe-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
