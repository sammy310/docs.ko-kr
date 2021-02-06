---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_FINALIZER_FLAGS'
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
ms.openlocfilehash: 96430b1ba3a38cce2801ed55f030395154c78dab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649184"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="c6491-103">COR_PRF_FINALIZER_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="c6491-103">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>

<span data-ttu-id="c6491-104">개체에 대한 종료자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6491-104">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6491-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6491-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c6491-106">구성원</span><span class="sxs-lookup"><span data-stu-id="c6491-106">Members</span></span>  
  
|<span data-ttu-id="c6491-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c6491-107">Member</span></span>|<span data-ttu-id="c6491-108">설명</span><span class="sxs-lookup"><span data-stu-id="c6491-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="c6491-109">종료자는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6491-109">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6491-110">설명</span><span class="sxs-lookup"><span data-stu-id="c6491-110">Remarks</span></span>  

 <span data-ttu-id="c6491-111">`COR_PRF_FINALIZER_FLAGS`열거형은 [ICorProfilerCallback2:: FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) 메서드에서 개체의 종료자를 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6491-111">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6491-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6491-112">Requirements</span></span>  

 <span data-ttu-id="c6491-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6491-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6491-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6491-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6491-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6491-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6491-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6491-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6491-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6491-117">See also</span></span>

- [<span data-ttu-id="c6491-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="c6491-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
