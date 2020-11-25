---
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
ms.openlocfilehash: 028395b1c8677d07d4a6481740ecdc7ebb48c180
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718529"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="f7627-102">COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="f7627-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>

<span data-ttu-id="f7627-103">왼쪽에서 오른쪽 순서로 연속적으로 메모리에 저장한 함수 인수 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7627-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7627-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7627-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="f7627-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f7627-105">Members</span></span>  
  
|<span data-ttu-id="f7627-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f7627-106">Members</span></span>|<span data-ttu-id="f7627-107">설명</span><span class="sxs-lookup"><span data-stu-id="f7627-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="f7627-108">블록의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f7627-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="f7627-109">연속 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="f7627-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7627-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7627-110">Requirements</span></span>  

 <span data-ttu-id="f7627-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7627-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7627-112">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="f7627-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f7627-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7627-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7627-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7627-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7627-115">참조</span><span class="sxs-lookup"><span data-stu-id="f7627-115">See also</span></span>

- [<span data-ttu-id="f7627-116">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="f7627-116">Profiling Structures</span></span>](profiling-structures.md)
