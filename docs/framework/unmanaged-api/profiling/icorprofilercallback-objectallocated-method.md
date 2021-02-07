---
description: 'ICorProfilerCallback:: ObjectAllocated 된 메서드에 대해 자세히 알아보세요.'
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
ms.openlocfilehash: 58b58aeb4bb88d0df32cebc32440317a4d23632d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745166"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="8f68a-103">ICorProfilerCallback::ObjectAllocated 메서드</span><span class="sxs-lookup"><span data-stu-id="8f68a-103">ICorProfilerCallback::ObjectAllocated Method</span></span>

<span data-ttu-id="8f68a-104">힙에 있는 메모리가 개체에 할당 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8f68a-104">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f68a-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f68a-105">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f68a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f68a-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="8f68a-107">진행 메모리가 할당 된 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8f68a-107">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="8f68a-108">진행 개체가 인스턴스인 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8f68a-108">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f68a-109">설명</span><span class="sxs-lookup"><span data-stu-id="8f68a-109">Remarks</span></span>  

 <span data-ttu-id="8f68a-110">`ObjectedAllocated`스택 또는 관리 되지 않는 메모리의 할당에 대해 메서드가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f68a-110">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="8f68a-111">`classId`매개 변수는 아직 로드 되지 않은 관리 코드의 클래스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f68a-111">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="8f68a-112">프로파일러는 콜백 직후 해당 클래스에 대 한 클래스 로드 콜백을 받게 됩니다 `ObjectAllocated` .</span><span class="sxs-lookup"><span data-stu-id="8f68a-112">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f68a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f68a-113">Requirements</span></span>  

 <span data-ttu-id="8f68a-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f68a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f68a-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f68a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f68a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f68a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f68a-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f68a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f68a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f68a-118">See also</span></span>

- [<span data-ttu-id="8f68a-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f68a-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8f68a-120">ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="8f68a-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="8f68a-121">ClassLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="8f68a-121">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
