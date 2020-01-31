---
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
ms.openlocfilehash: bff45e6f6f57b95d07ac5073cb70020818cce000
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867167"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a><span data-ttu-id="fd903-102">COR_PRF_GC_ROOT_KIND 열거형</span><span class="sxs-lookup"><span data-stu-id="fd903-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="fd903-103">[ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 콜백에서 노출 하는 가비지 수집 루트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd903-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd903-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd903-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="fd903-105">Members</span><span class="sxs-lookup"><span data-stu-id="fd903-105">Members</span></span>  
  
|<span data-ttu-id="fd903-106">Member</span><span class="sxs-lookup"><span data-stu-id="fd903-106">Member</span></span>|<span data-ttu-id="fd903-107">설명</span><span class="sxs-lookup"><span data-stu-id="fd903-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="fd903-108">루트는 스택의 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fd903-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="fd903-109">루트는 종료자 큐의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fd903-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="fd903-110">루트가 가비지 수집 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="fd903-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="fd903-111">Root 종류가 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="fd903-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd903-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd903-112">Requirements</span></span>  
 <span data-ttu-id="fd903-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd903-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd903-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd903-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd903-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd903-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd903-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd903-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd903-117">참조</span><span class="sxs-lookup"><span data-stu-id="fd903-117">See also</span></span>

- [<span data-ttu-id="fd903-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="fd903-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
