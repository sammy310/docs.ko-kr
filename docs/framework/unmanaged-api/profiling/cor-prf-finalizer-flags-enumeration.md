---
title: COR_PRF_FINALIZER_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
ms.openlocfilehash: 2b766715d6d87ab17a7cdabf721bbebf67e1ff13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718581"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="b6cc5-102">COR_PRF_FINALIZER_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="b6cc5-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>

<span data-ttu-id="b6cc5-103">개체에 대한 종료자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cc5-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6cc5-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6cc5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b6cc5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b6cc5-105">Members</span></span>  
  
|<span data-ttu-id="b6cc5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b6cc5-106">Member</span></span>|<span data-ttu-id="b6cc5-107">설명</span><span class="sxs-lookup"><span data-stu-id="b6cc5-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="b6cc5-108">종료자는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cc5-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6cc5-109">설명</span><span class="sxs-lookup"><span data-stu-id="b6cc5-109">Remarks</span></span>  

 <span data-ttu-id="b6cc5-110">`COR_PRF_FINALIZER_FLAGS`열거형은 [ICorProfilerCallback2:: FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) 메서드에서 개체의 종료자를 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cc5-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6cc5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6cc5-111">Requirements</span></span>  

 <span data-ttu-id="b6cc5-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6cc5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6cc5-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6cc5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b6cc5-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6cc5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6cc5-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6cc5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cc5-116">참조</span><span class="sxs-lookup"><span data-stu-id="b6cc5-116">See also</span></span>

- [<span data-ttu-id="b6cc5-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="b6cc5-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
