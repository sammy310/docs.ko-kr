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
ms.openlocfilehash: 5e718d05f033cc46fa460a81f6816a13ec32476d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428352"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="a099e-102">COR_PRF_FINALIZER_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="a099e-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="a099e-103">개체에 대한 종료자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a099e-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a099e-104">구문</span><span class="sxs-lookup"><span data-stu-id="a099e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a099e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a099e-105">Members</span></span>  
  
|<span data-ttu-id="a099e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a099e-106">Member</span></span>|<span data-ttu-id="a099e-107">설명</span><span class="sxs-lookup"><span data-stu-id="a099e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="a099e-108">종료자는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a099e-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a099e-109">주의</span><span class="sxs-lookup"><span data-stu-id="a099e-109">Remarks</span></span>  
 <span data-ttu-id="a099e-110">`COR_PRF_FINALIZER_FLAGS` 열거형은 [ICorProfilerCallback2:: FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) 메서드에서 개체의 종료자를 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a099e-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a099e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a099e-111">Requirements</span></span>  
 <span data-ttu-id="a099e-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a099e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a099e-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a099e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a099e-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a099e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a099e-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a099e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a099e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a099e-116">See also</span></span>

- [<span data-ttu-id="a099e-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="a099e-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
