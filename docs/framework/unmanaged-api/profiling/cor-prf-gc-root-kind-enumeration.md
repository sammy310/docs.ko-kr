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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7dfbba3cef8afadfc6e12e53ea328c4fc7165ca0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206761"
---
# <a name="corprfgcrootkind-enumeration"></a><span data-ttu-id="21ff7-102">COR_PRF_GC_ROOT_KIND 열거형</span><span class="sxs-lookup"><span data-stu-id="21ff7-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="21ff7-103">에 의해 노출 되는 가비지 컬렉션 루트의 종류를 나타내는 합니다 [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ff7-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21ff7-104">구문</span><span class="sxs-lookup"><span data-stu-id="21ff7-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="21ff7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="21ff7-105">Members</span></span>  
  
|<span data-ttu-id="21ff7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="21ff7-106">Member</span></span>|<span data-ttu-id="21ff7-107">설명</span><span class="sxs-lookup"><span data-stu-id="21ff7-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="21ff7-108">루트 스택에 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="21ff7-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="21ff7-109">루트는 종료자 큐의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="21ff7-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="21ff7-110">루트는 가비지 컬렉션 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="21ff7-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="21ff7-111">루트 종류가 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21ff7-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21ff7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21ff7-112">Requirements</span></span>  
 <span data-ttu-id="21ff7-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="21ff7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21ff7-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21ff7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21ff7-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21ff7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21ff7-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21ff7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ff7-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="21ff7-117">See also</span></span>

- [<span data-ttu-id="21ff7-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="21ff7-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
