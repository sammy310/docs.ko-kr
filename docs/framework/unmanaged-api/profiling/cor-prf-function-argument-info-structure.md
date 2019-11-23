---
title: COR_PRF_FUNCTION_ARGUMENT_INFO 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: 2b01acbd617b13a64ef3dca6c8661f1e6bb067ac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447389"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="b7173-102">COR_PRF_FUNCTION_ARGUMENT_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="b7173-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="b7173-103">왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7173-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7173-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7173-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b7173-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b7173-105">Members</span></span>  
  
|<span data-ttu-id="b7173-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b7173-106">Member</span></span>|<span data-ttu-id="b7173-107">설명</span><span class="sxs-lookup"><span data-stu-id="b7173-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="b7173-108">The number of blocks of arguments.</span><span class="sxs-lookup"><span data-stu-id="b7173-108">The number of blocks of arguments.</span></span> <span data-ttu-id="b7173-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span><span class="sxs-lookup"><span data-stu-id="b7173-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="b7173-110">The total size of all arguments.</span><span class="sxs-lookup"><span data-stu-id="b7173-110">The total size of all arguments.</span></span> <span data-ttu-id="b7173-111">In other words, this value is the sum of the argument lengths.</span><span class="sxs-lookup"><span data-stu-id="b7173-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="b7173-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span><span class="sxs-lookup"><span data-stu-id="b7173-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7173-113">주의</span><span class="sxs-lookup"><span data-stu-id="b7173-113">Remarks</span></span>  
 <span data-ttu-id="b7173-114">A function may have many arguments.</span><span class="sxs-lookup"><span data-stu-id="b7173-114">A function may have many arguments.</span></span> <span data-ttu-id="b7173-115">Those arguments might not be stored contiguously in memory.</span><span class="sxs-lookup"><span data-stu-id="b7173-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="b7173-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span><span class="sxs-lookup"><span data-stu-id="b7173-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="b7173-117">These arguments are all for the same function; they're just stored in different places.</span><span class="sxs-lookup"><span data-stu-id="b7173-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="b7173-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span><span class="sxs-lookup"><span data-stu-id="b7173-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="b7173-119">It uses an array to reference all the blocks of function arguments.</span><span class="sxs-lookup"><span data-stu-id="b7173-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="b7173-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span><span class="sxs-lookup"><span data-stu-id="b7173-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="b7173-121">Arguments that are stored in registers are spilled into memory to build the structures.</span><span class="sxs-lookup"><span data-stu-id="b7173-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7173-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7173-122">Requirements</span></span>  
 <span data-ttu-id="b7173-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7173-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7173-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="b7173-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b7173-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7173-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7173-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7173-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7173-127">참조</span><span class="sxs-lookup"><span data-stu-id="b7173-127">See also</span></span>

- [<span data-ttu-id="b7173-128">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="b7173-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
