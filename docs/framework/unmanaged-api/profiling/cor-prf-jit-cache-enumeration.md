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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cdbe36403f830926d611ffdc655d82ea25ddeef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144796"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="2dbb0-102">COR_PRF_JIT_CACHE 열거형</span><span class="sxs-lookup"><span data-stu-id="2dbb0-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="2dbb0-103">캐시된 함수 검색의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2dbb0-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND` <span data-ttu-id="2dbb0-104">값이 0 이면 높으므로 `COR_PRF_JIT_CACHE` 를 부울 대신 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2dbb0-104">has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dbb0-105">구문</span><span class="sxs-lookup"><span data-stu-id="2dbb0-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="2dbb0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2dbb0-106">Members</span></span>  
  
|<span data-ttu-id="2dbb0-107">멤버</span><span class="sxs-lookup"><span data-stu-id="2dbb0-107">Member</span></span>|<span data-ttu-id="2dbb0-108">설명</span><span class="sxs-lookup"><span data-stu-id="2dbb0-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="2dbb0-109">검색 함수를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dbb0-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="2dbb0-110">검색 함수를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2dbb0-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2dbb0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dbb0-111">Requirements</span></span>  
 <span data-ttu-id="2dbb0-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2dbb0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dbb0-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2dbb0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2dbb0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dbb0-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2dbb0-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="2dbb0-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2dbb0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="2dbb0-116">See also</span></span>

- [<span data-ttu-id="2dbb0-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="2dbb0-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
