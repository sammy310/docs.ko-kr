---
description: '다음에 대 한 자세한 정보: COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체'
title: COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
ms.openlocfilehash: 65d762ba4513341b20426ea56d423a2066f6e714
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649015"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="93fe8-103">COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="93fe8-103">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>

<span data-ttu-id="93fe8-104">왼쪽에서 오른쪽 순서로 연속적으로 메모리에 저장한 함수 인수 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93fe8-104">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93fe8-105">구문</span><span class="sxs-lookup"><span data-stu-id="93fe8-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="93fe8-106">구성원</span><span class="sxs-lookup"><span data-stu-id="93fe8-106">Members</span></span>  
  
|<span data-ttu-id="93fe8-107">구성원</span><span class="sxs-lookup"><span data-stu-id="93fe8-107">Members</span></span>|<span data-ttu-id="93fe8-108">설명</span><span class="sxs-lookup"><span data-stu-id="93fe8-108">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="93fe8-109">블록의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="93fe8-109">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="93fe8-110">연속 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="93fe8-110">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93fe8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93fe8-111">Requirements</span></span>  

 <span data-ttu-id="93fe8-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93fe8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93fe8-113">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="93fe8-113">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="93fe8-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93fe8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93fe8-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93fe8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93fe8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93fe8-116">See also</span></span>

- [<span data-ttu-id="93fe8-117">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="93fe8-117">Profiling Structures</span></span>](profiling-structures.md)
