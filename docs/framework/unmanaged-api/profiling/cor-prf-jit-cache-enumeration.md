---
title: COR_PRF_JIT_CACHE 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
ms.openlocfilehash: 0061e0772c48626a7ba88280e44b74ef32838a41
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867141"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="fb0e3-102">COR_PRF_JIT_CACHE 열거형</span><span class="sxs-lookup"><span data-stu-id="fb0e3-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="fb0e3-103">캐시된 함수 검색의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb0e3-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb0e3-104">`COR_PRF_CACHED_FUNCTION_FOUND` 값이 0 이므로 `COR_PRF_JIT_CACHE` 부울 서로게이트로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0e3-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb0e3-105">구문</span><span class="sxs-lookup"><span data-stu-id="fb0e3-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="fb0e3-106">Members</span><span class="sxs-lookup"><span data-stu-id="fb0e3-106">Members</span></span>  
  
|<span data-ttu-id="fb0e3-107">Member</span><span class="sxs-lookup"><span data-stu-id="fb0e3-107">Member</span></span>|<span data-ttu-id="fb0e3-108">설명</span><span class="sxs-lookup"><span data-stu-id="fb0e3-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="fb0e3-109">검색에서 함수를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0e3-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="fb0e3-110">검색에서 함수를 찾지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb0e3-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb0e3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb0e3-111">Requirements</span></span>  
 <span data-ttu-id="fb0e3-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb0e3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb0e3-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb0e3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb0e3-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb0e3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb0e3-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb0e3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb0e3-116">참조</span><span class="sxs-lookup"><span data-stu-id="fb0e3-116">See also</span></span>

- [<span data-ttu-id="fb0e3-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="fb0e3-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
