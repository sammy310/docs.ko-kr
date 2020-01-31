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
ms.openlocfilehash: 1c3c311fd431b6c0b18af3d6516973b2471cfabd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867063"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="c1d02-102">COR_PRF_TRANSITION_REASON 열거형</span><span class="sxs-lookup"><span data-stu-id="c1d02-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="c1d02-103">관리 코드에서 비관리 코드로 전환 또는 그 반대의 경우로 전환하는 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1d02-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1d02-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1d02-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="c1d02-105">Members</span><span class="sxs-lookup"><span data-stu-id="c1d02-105">Members</span></span>  
  
|<span data-ttu-id="c1d02-106">Member</span><span class="sxs-lookup"><span data-stu-id="c1d02-106">Member</span></span>|<span data-ttu-id="c1d02-107">설명</span><span class="sxs-lookup"><span data-stu-id="c1d02-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="c1d02-108">함수 호출로 인해 전환이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d02-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="c1d02-109">이 전환은 함수에서의 반환 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d02-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1d02-110">주의</span><span class="sxs-lookup"><span data-stu-id="c1d02-110">Remarks</span></span>  
 <span data-ttu-id="c1d02-111">전환이 발생 하면 프로파일러는 [ICorProfilerCallback:: ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) 또는 [ICorProfilerCallback:: UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback을 받습니다 .이 중 하나는 `COR_PRF_TRANSITION_REASON` 열거형의 값을 제공 하 여 전환 이유를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d02-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1d02-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1d02-112">Requirements</span></span>  
 <span data-ttu-id="c1d02-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1d02-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1d02-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1d02-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1d02-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1d02-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1d02-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1d02-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
