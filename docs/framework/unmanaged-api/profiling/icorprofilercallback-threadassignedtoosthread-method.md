---
description: '자세히 알아보기: ICorProfilerCallback:: ThreadAssignedToOSThread 메서드'
title: ICorProfilerCallback::ThreadAssignedToOSThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
ms.openlocfilehash: 04fba4cabb0ac58b3afeaae1fd579865335a9e14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647988"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="72608-103">ICorProfilerCallback::ThreadAssignedToOSThread 메서드</span><span class="sxs-lookup"><span data-stu-id="72608-103">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>

<span data-ttu-id="72608-104">특정 운영 체제 스레드를 사용 하 여 관리 되는 스레드가 구현 중임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="72608-104">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72608-105">구문</span><span class="sxs-lookup"><span data-stu-id="72608-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72608-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72608-106">Parameters</span></span>  

 `managedThreadId`  
 <span data-ttu-id="72608-107">진행 관리 되는 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="72608-107">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="72608-108">진행 운영 체제 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="72608-108">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72608-109">설명</span><span class="sxs-lookup"><span data-stu-id="72608-109">Remarks</span></span>  

 <span data-ttu-id="72608-110">`ThreadAssignedToOSThread`콜백은 프로파일러가 운영 체제 스레드의 파이버에서 관리 되는 스레드에 대 한 정확한 매핑을 유지할 수 있도록 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="72608-110">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72608-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72608-111">Requirements</span></span>  

 <span data-ttu-id="72608-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72608-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72608-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72608-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72608-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72608-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72608-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72608-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72608-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72608-116">See also</span></span>

- [<span data-ttu-id="72608-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72608-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
