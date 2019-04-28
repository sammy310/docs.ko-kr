---
title: COR_PRF_TRANSITION_REASON 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2556196b7c8f81709e6880962e8ff36e126dd8b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599041"
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="45f68-102">COR_PRF_TRANSITION_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="45f68-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="45f68-103">관리 코드에서 비관리 코드로 전환 또는 그 반대의 경우로 전환하는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45f68-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45f68-104">구문</span><span class="sxs-lookup"><span data-stu-id="45f68-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="45f68-105">멤버</span><span class="sxs-lookup"><span data-stu-id="45f68-105">Members</span></span>  
  
|<span data-ttu-id="45f68-106">멤버</span><span class="sxs-lookup"><span data-stu-id="45f68-106">Member</span></span>|<span data-ttu-id="45f68-107">설명</span><span class="sxs-lookup"><span data-stu-id="45f68-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="45f68-108">전환 하는 함수 호출 되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="45f68-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="45f68-109">전환 함수에서 반환 되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="45f68-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45f68-110">설명</span><span class="sxs-lookup"><span data-stu-id="45f68-110">Remarks</span></span>  
 <span data-ttu-id="45f68-111">전환이 발생 하면 프로파일러 수신를 [icorprofilercallback:: Managedtounmanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) 하거나 [icorprofilercallback:: Unmanagedtomanagedtransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) 콜백 하는 중 값을 제공 하는 `COR_PRF_TRANSITION_REASON` 전환에 대 한 이유를 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="45f68-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45f68-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45f68-112">Requirements</span></span>  
 <span data-ttu-id="45f68-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="45f68-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45f68-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45f68-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45f68-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45f68-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45f68-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45f68-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
