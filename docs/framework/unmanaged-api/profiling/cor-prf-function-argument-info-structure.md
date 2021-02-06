---
description: '다음에 대 한 자세한 정보: COR_PRF_FUNCTION_ARGUMENT_INFO 구조체'
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
ms.openlocfilehash: c40c9b20dad79fa36a1ed4471106a54f2c55b422
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649067"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="6cdfe-103">COR_PRF_FUNCTION_ARGUMENT_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="6cdfe-103">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>

<span data-ttu-id="6cdfe-104">왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-104">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cdfe-105">구문</span><span class="sxs-lookup"><span data-stu-id="6cdfe-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="6cdfe-106">구성원</span><span class="sxs-lookup"><span data-stu-id="6cdfe-106">Members</span></span>  
  
|<span data-ttu-id="6cdfe-107">멤버</span><span class="sxs-lookup"><span data-stu-id="6cdfe-107">Member</span></span>|<span data-ttu-id="6cdfe-108">설명</span><span class="sxs-lookup"><span data-stu-id="6cdfe-108">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="6cdfe-109">인수의 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-109">The number of blocks of arguments.</span></span> <span data-ttu-id="6cdfe-110">즉,이 값은 배열에 있는 [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) 구조체의 수입니다 `ranges` .</span><span class="sxs-lookup"><span data-stu-id="6cdfe-110">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="6cdfe-111">모든 인수의 전체 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-111">The total size of all arguments.</span></span> <span data-ttu-id="6cdfe-112">즉,이 값은 인수 길이의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-112">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="6cdfe-113">`COR_PRF_FUNCTION_ARGUMENT_RANGE`각각 하나의 함수 인수 블록을 나타내는 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-113">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cdfe-114">설명</span><span class="sxs-lookup"><span data-stu-id="6cdfe-114">Remarks</span></span>  

 <span data-ttu-id="6cdfe-115">함수에는 여러 개의 인수가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-115">A function may have many arguments.</span></span> <span data-ttu-id="6cdfe-116">이러한 인수는 메모리에 연속적으로 저장 되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-116">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="6cdfe-117">한 곳에 세 개의 인수 블록, 다른 위치의 두 인수 블록, 다른 위치의 한 인수에 대 한 최종 블록이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-117">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="6cdfe-118">이러한 인수는 모두 동일한 함수에 대해입니다. 다른 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-118">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="6cdfe-119">`COR_PRF_FUNCTION_ARGUMENT_INFO`구조체는 단일 함수의 모든 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-119">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="6cdfe-120">배열을 사용 하 여 함수 인수의 모든 블록을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-120">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="6cdfe-121">따라서 단일 함수의 경우 `COR_PRF_FUNCTION_ARGUMENT_INFO` `COR_PRF_FUNCTION_ARGUMENT_RANGE` 하나 이상의 함수 인수를 가리키는 여러 구조체를 참조 하는 단일 구조체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-121">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="6cdfe-122">레지스터에 저장 된 인수는 메모리에 분산 되어 구조를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-122">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cdfe-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6cdfe-123">Requirements</span></span>  

 <span data-ttu-id="6cdfe-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cdfe-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cdfe-125">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="6cdfe-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6cdfe-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cdfe-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cdfe-127">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cdfe-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cdfe-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cdfe-128">See also</span></span>

- [<span data-ttu-id="6cdfe-129">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="6cdfe-129">Profiling Structures</span></span>](profiling-structures.md)
