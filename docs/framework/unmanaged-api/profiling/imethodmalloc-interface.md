---
description: '자세한 정보: IMethodMalloc 인터페이스'
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
ms.openlocfilehash: 6b84ac0ddb49718d24b2cad174613bc311dc509b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736962"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="923e6-103">IMethodMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="923e6-103">IMethodMalloc Interface</span></span>

<span data-ttu-id="923e6-104">새 MSIL (Microsoft 중간 언어) 함수 본문에 대 한 메모리를 할당 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="923e6-104">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="923e6-105">`IMethodMalloc`인터페이스는 단순 메모리 할당자입니다.</span><span class="sxs-lookup"><span data-stu-id="923e6-105">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="923e6-106">메모리를 할당할 수 있지만 해제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="923e6-106">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="923e6-107">메서드</span><span class="sxs-lookup"><span data-stu-id="923e6-107">Methods</span></span>  
  
|<span data-ttu-id="923e6-108">메서드</span><span class="sxs-lookup"><span data-stu-id="923e6-108">Method</span></span>|<span data-ttu-id="923e6-109">설명</span><span class="sxs-lookup"><span data-stu-id="923e6-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="923e6-110">Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="923e6-110">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="923e6-111">새 MSIL 함수 본문에 지정 된 크기의 메모리를 할당 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="923e6-111">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="923e6-112">설명</span><span class="sxs-lookup"><span data-stu-id="923e6-112">Remarks</span></span>  

 <span data-ttu-id="923e6-113">각 할당자는 모듈에 따라 달라 지 며 함수 본문은 모듈의 기본에서 양의 오프셋에 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="923e6-113">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="923e6-114">모듈의 기본 위에 있는 메모리는 유용 하므로 할당자를 사용 하 여 함수 본문에 대해서만 메모리를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="923e6-114">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="923e6-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="923e6-115">Requirements</span></span>  

 <span data-ttu-id="923e6-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="923e6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="923e6-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="923e6-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="923e6-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="923e6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="923e6-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="923e6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="923e6-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="923e6-120">See also</span></span>

- [<span data-ttu-id="923e6-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="923e6-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
