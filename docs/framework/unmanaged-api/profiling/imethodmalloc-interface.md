---
title: IMethodMalloc 인터페이스
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 3f840154d472dbcea7dfef7ba93e38c80b836734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447553"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="05293-102">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05293-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="05293-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span><span class="sxs-lookup"><span data-stu-id="05293-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05293-104">The `IMethodMalloc` interface is a simple memory allocator.</span><span class="sxs-lookup"><span data-stu-id="05293-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="05293-105">It allows you to allocate memory, but not to free it.</span><span class="sxs-lookup"><span data-stu-id="05293-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05293-106">메서드</span><span class="sxs-lookup"><span data-stu-id="05293-106">Methods</span></span>  
  
|<span data-ttu-id="05293-107">메서드</span><span class="sxs-lookup"><span data-stu-id="05293-107">Method</span></span>|<span data-ttu-id="05293-108">설명</span><span class="sxs-lookup"><span data-stu-id="05293-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05293-109">Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="05293-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="05293-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span><span class="sxs-lookup"><span data-stu-id="05293-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05293-111">주의</span><span class="sxs-lookup"><span data-stu-id="05293-111">Remarks</span></span>  
 <span data-ttu-id="05293-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span><span class="sxs-lookup"><span data-stu-id="05293-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="05293-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span><span class="sxs-lookup"><span data-stu-id="05293-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05293-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05293-114">Requirements</span></span>  
 <span data-ttu-id="05293-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05293-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05293-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="05293-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="05293-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05293-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05293-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05293-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05293-119">참조</span><span class="sxs-lookup"><span data-stu-id="05293-119">See also</span></span>

- [<span data-ttu-id="05293-120">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05293-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
