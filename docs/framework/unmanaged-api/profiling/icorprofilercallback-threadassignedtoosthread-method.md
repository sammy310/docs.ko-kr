---
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
ms.openlocfilehash: 0e8c91f65d4ebec07689a42d4517fc100fce136d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865846"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="efbca-102">ICorProfilerCallback::ThreadAssignedToOSThread 메서드</span><span class="sxs-lookup"><span data-stu-id="efbca-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="efbca-103">특정 운영 체제 스레드를 사용 하 여 관리 되는 스레드가 구현 중임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="efbca-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efbca-104">구문</span><span class="sxs-lookup"><span data-stu-id="efbca-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efbca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="efbca-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="efbca-106">진행 관리 되는 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="efbca-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="efbca-107">진행 운영 체제 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="efbca-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efbca-108">주의</span><span class="sxs-lookup"><span data-stu-id="efbca-108">Remarks</span></span>  
 <span data-ttu-id="efbca-109">프로파일러가 운영 체제 스레드의 파이버에서 관리 되는 스레드에 대 한 정확한 매핑을 유지할 수 있도록 `ThreadAssignedToOSThread` 콜백이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbca-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efbca-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="efbca-110">Requirements</span></span>  
 <span data-ttu-id="efbca-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efbca-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efbca-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="efbca-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="efbca-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efbca-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efbca-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efbca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efbca-115">참조</span><span class="sxs-lookup"><span data-stu-id="efbca-115">See also</span></span>

- [<span data-ttu-id="efbca-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efbca-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
