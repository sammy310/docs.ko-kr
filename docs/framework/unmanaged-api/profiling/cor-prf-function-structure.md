---
title: COR_PRF_FUNCTION 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
ms.openlocfilehash: 856e01c7934709a17556aa53851204bf6a917de8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500938"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="c9287-102">COR_PRF_FUNCTION 구조체</span><span class="sxs-lookup"><span data-stu-id="c9287-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="c9287-103">함수의 ID와 다시 컴파일된 함수 버전의 ID를 결합하여 함수의 고유한 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9287-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9287-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9287-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="c9287-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c9287-105">Members</span></span>  
  
|<span data-ttu-id="c9287-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c9287-106">Member</span></span>|<span data-ttu-id="c9287-107">설명</span><span class="sxs-lookup"><span data-stu-id="c9287-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="c9287-108">함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c9287-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="c9287-109">다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c9287-109">The ID of the recompiled function.</span></span> <span data-ttu-id="c9287-110">값이 0 이면 함수의 원래 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9287-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9287-111">설명</span><span class="sxs-lookup"><span data-stu-id="c9287-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9287-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9287-112">Requirements</span></span>  
 <span data-ttu-id="c9287-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9287-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9287-114">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="c9287-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c9287-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9287-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9287-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9287-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9287-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9287-117">See also</span></span>

- [<span data-ttu-id="c9287-118">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="c9287-118">Profiling Structures</span></span>](profiling-structures.md)
