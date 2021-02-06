---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_JIT_CACHE'
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
ms.openlocfilehash: 94b04b42504760be826f78cee0da3066f1936f32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648755"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="6ea8e-103">COR_PRF_JIT_CACHE 열거형</span><span class="sxs-lookup"><span data-stu-id="6ea8e-103">COR_PRF_JIT_CACHE Enumeration</span></span>

<span data-ttu-id="6ea8e-104">캐시된 함수 검색의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ea8e-104">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ea8e-105">`COR_PRF_CACHED_FUNCTION_FOUND` 의 값이 0 이므로 `COR_PRF_JIT_CACHE` 부울 서로게이트로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea8e-105">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea8e-106">구문</span><span class="sxs-lookup"><span data-stu-id="6ea8e-106">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="6ea8e-107">구성원</span><span class="sxs-lookup"><span data-stu-id="6ea8e-107">Members</span></span>  
  
|<span data-ttu-id="6ea8e-108">멤버</span><span class="sxs-lookup"><span data-stu-id="6ea8e-108">Member</span></span>|<span data-ttu-id="6ea8e-109">설명</span><span class="sxs-lookup"><span data-stu-id="6ea8e-109">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="6ea8e-110">검색에서 함수를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea8e-110">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="6ea8e-111">검색에서 함수를 찾지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea8e-111">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ea8e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ea8e-112">Requirements</span></span>  

 <span data-ttu-id="6ea8e-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ea8e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea8e-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ea8e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ea8e-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ea8e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ea8e-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea8e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea8e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ea8e-117">See also</span></span>

- [<span data-ttu-id="6ea8e-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="6ea8e-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
