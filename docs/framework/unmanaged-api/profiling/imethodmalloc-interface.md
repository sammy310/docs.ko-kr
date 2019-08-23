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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c67ce15175f8667139f99cec1ed17531eab473e1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935655"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="a72df-102">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a72df-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="a72df-103">새 MSIL (Microsoft 중간 언어) 함수 본문에 대 한 메모리를 할당 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a72df-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a72df-104">인터페이스 `IMethodMalloc` 는 단순 메모리 할당자입니다.</span><span class="sxs-lookup"><span data-stu-id="a72df-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="a72df-105">메모리를 할당할 수 있지만 해제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a72df-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a72df-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a72df-106">Methods</span></span>  
  
|<span data-ttu-id="a72df-107">메서드</span><span class="sxs-lookup"><span data-stu-id="a72df-107">Method</span></span>|<span data-ttu-id="a72df-108">Description</span><span class="sxs-lookup"><span data-stu-id="a72df-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a72df-109">Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="a72df-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="a72df-110">새 MSIL 함수 본문에 지정 된 크기의 메모리를 할당 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a72df-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a72df-111">설명</span><span class="sxs-lookup"><span data-stu-id="a72df-111">Remarks</span></span>  
 <span data-ttu-id="a72df-112">각 할당자는 모듈에 따라 달라 지 며 함수 본문은 모듈의 기본에서 양의 오프셋에 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a72df-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="a72df-113">모듈의 기본 위에 있는 메모리는 유용 하므로 할당자를 사용 하 여 함수 본문에 대해서만 메모리를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a72df-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a72df-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a72df-114">Requirements</span></span>  
 <span data-ttu-id="a72df-115">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a72df-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a72df-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a72df-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a72df-117">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a72df-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a72df-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a72df-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72df-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="a72df-119">See also</span></span>

- [<span data-ttu-id="a72df-120">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a72df-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
