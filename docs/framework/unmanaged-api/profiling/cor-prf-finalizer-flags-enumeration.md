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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a66b2b94765c3d59327e500f1e208dc93cd8e231
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781930"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="92c11-102">COR_PRF_FINALIZER_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="92c11-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="92c11-103">개체에 대한 종료자를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92c11-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c11-104">구문</span><span class="sxs-lookup"><span data-stu-id="92c11-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="92c11-105">멤버</span><span class="sxs-lookup"><span data-stu-id="92c11-105">Members</span></span>  
  
|<span data-ttu-id="92c11-106">멤버</span><span class="sxs-lookup"><span data-stu-id="92c11-106">Member</span></span>|<span data-ttu-id="92c11-107">설명</span><span class="sxs-lookup"><span data-stu-id="92c11-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="92c11-108">종료 자가 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c11-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92c11-109">설명</span><span class="sxs-lookup"><span data-stu-id="92c11-109">Remarks</span></span>  
 <span data-ttu-id="92c11-110">합니다 `COR_PRF_FINALIZER_FLAGS` 열거형에서 사용 되는 [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) 개체에 대 한 종료자를 설명 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="92c11-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c11-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92c11-111">Requirements</span></span>  
 <span data-ttu-id="92c11-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="92c11-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92c11-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92c11-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92c11-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92c11-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92c11-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92c11-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c11-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="92c11-116">See also</span></span>

- [<span data-ttu-id="92c11-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="92c11-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
