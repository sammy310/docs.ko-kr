---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_GC_ROOT_KIND'
title: COR_PRF_GC_ROOT_KIND 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
ms.openlocfilehash: 148d48458c906974d76b9e0ec0cb6b4d15ee49ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648781"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a><span data-ttu-id="a7467-103">COR_PRF_GC_ROOT_KIND 열거형</span><span class="sxs-lookup"><span data-stu-id="a7467-103">COR_PRF_GC_ROOT_KIND Enumeration</span></span>

<span data-ttu-id="a7467-104">[ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 콜백에서 노출 하는 가비지 수집 루트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7467-104">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7467-105">구문</span><span class="sxs-lookup"><span data-stu-id="a7467-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="a7467-106">구성원</span><span class="sxs-lookup"><span data-stu-id="a7467-106">Members</span></span>  
  
|<span data-ttu-id="a7467-107">멤버</span><span class="sxs-lookup"><span data-stu-id="a7467-107">Member</span></span>|<span data-ttu-id="a7467-108">설명</span><span class="sxs-lookup"><span data-stu-id="a7467-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="a7467-109">루트는 스택의 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7467-109">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="a7467-110">루트는 종료자 큐의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="a7467-110">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="a7467-111">루트가 가비지 수집 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="a7467-111">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="a7467-112">Root 종류가 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a7467-112">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7467-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7467-113">Requirements</span></span>  

 <span data-ttu-id="a7467-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7467-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7467-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7467-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7467-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7467-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7467-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7467-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7467-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7467-118">See also</span></span>

- [<span data-ttu-id="a7467-119">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="a7467-119">Profiling Enumerations</span></span>](profiling-enumerations.md)
