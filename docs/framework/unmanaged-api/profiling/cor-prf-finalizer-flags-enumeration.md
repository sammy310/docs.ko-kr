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
ms.openlocfilehash: b273faafd7abb86ace58bb5c24473406af3ce20e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500977"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="32a24-102">COR_PRF_FINALIZER_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="32a24-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="32a24-103">개체에 대한 종료자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32a24-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32a24-104">구문</span><span class="sxs-lookup"><span data-stu-id="32a24-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="32a24-105">멤버</span><span class="sxs-lookup"><span data-stu-id="32a24-105">Members</span></span>  
  
|<span data-ttu-id="32a24-106">멤버</span><span class="sxs-lookup"><span data-stu-id="32a24-106">Member</span></span>|<span data-ttu-id="32a24-107">설명</span><span class="sxs-lookup"><span data-stu-id="32a24-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="32a24-108">종료자는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="32a24-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32a24-109">설명</span><span class="sxs-lookup"><span data-stu-id="32a24-109">Remarks</span></span>  
 <span data-ttu-id="32a24-110">`COR_PRF_FINALIZER_FLAGS`열거형은 [ICorProfilerCallback2:: FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) 메서드에서 개체의 종료자를 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32a24-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32a24-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32a24-111">Requirements</span></span>  
 <span data-ttu-id="32a24-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32a24-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32a24-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="32a24-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="32a24-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32a24-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32a24-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32a24-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32a24-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32a24-116">See also</span></span>

- [<span data-ttu-id="32a24-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="32a24-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
