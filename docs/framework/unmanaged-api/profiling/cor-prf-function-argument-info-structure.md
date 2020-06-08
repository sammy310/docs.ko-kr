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
ms.openlocfilehash: 9fca75ae59b95a226b51768b3e1bfb220d9926f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500964"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="47c24-102">COR_PRF_FUNCTION_ARGUMENT_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="47c24-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="47c24-103">왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c24-104">구문</span><span class="sxs-lookup"><span data-stu-id="47c24-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="47c24-105">멤버</span><span class="sxs-lookup"><span data-stu-id="47c24-105">Members</span></span>  
  
|<span data-ttu-id="47c24-106">멤버</span><span class="sxs-lookup"><span data-stu-id="47c24-106">Member</span></span>|<span data-ttu-id="47c24-107">설명</span><span class="sxs-lookup"><span data-stu-id="47c24-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="47c24-108">인수의 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-108">The number of blocks of arguments.</span></span> <span data-ttu-id="47c24-109">즉,이 값은 배열에 있는 [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) 구조체의 수입니다 `ranges` .</span><span class="sxs-lookup"><span data-stu-id="47c24-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="47c24-110">모든 인수의 전체 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-110">The total size of all arguments.</span></span> <span data-ttu-id="47c24-111">즉,이 값은 인수 길이의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="47c24-112">`COR_PRF_FUNCTION_ARGUMENT_RANGE`각각 하나의 함수 인수 블록을 나타내는 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47c24-113">설명</span><span class="sxs-lookup"><span data-stu-id="47c24-113">Remarks</span></span>  
 <span data-ttu-id="47c24-114">함수에는 여러 개의 인수가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-114">A function may have many arguments.</span></span> <span data-ttu-id="47c24-115">이러한 인수는 메모리에 연속적으로 저장 되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="47c24-116">한 곳에 세 개의 인수 블록, 다른 위치의 두 인수 블록, 다른 위치의 한 인수에 대 한 최종 블록이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="47c24-117">이러한 인수는 모두 동일한 함수에 대해입니다. 다른 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="47c24-118">`COR_PRF_FUNCTION_ARGUMENT_INFO`구조체는 단일 함수의 모든 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="47c24-119">배열을 사용 하 여 함수 인수의 모든 블록을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="47c24-120">따라서 단일 함수의 경우 `COR_PRF_FUNCTION_ARGUMENT_INFO` `COR_PRF_FUNCTION_ARGUMENT_RANGE` 하나 이상의 함수 인수를 가리키는 여러 구조체를 참조 하는 단일 구조체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="47c24-121">레지스터에 저장 된 인수는 메모리에 분산 되어 구조를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c24-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c24-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47c24-122">Requirements</span></span>  
 <span data-ttu-id="47c24-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47c24-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47c24-124">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="47c24-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="47c24-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47c24-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47c24-126">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47c24-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c24-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47c24-127">See also</span></span>

- [<span data-ttu-id="47c24-128">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="47c24-128">Profiling Structures</span></span>](profiling-structures.md)
