---
title: GetCachePath 함수
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1c28f32a4b24393483241bd2d7d6f550b8b65ba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796900"
---
# <a name="getcachepath-function"></a><span data-ttu-id="7727d-102">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="7727d-102">GetCachePath Function</span></span>
<span data-ttu-id="7727d-103">지정 된 플래그를 사용 하 여 캐시 된 어셈블리에 대 한 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7727d-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7727d-104">구문</span><span class="sxs-lookup"><span data-stu-id="7727d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="7727d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7727d-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="7727d-106">진행 캐시 된 어셈블리의 소스를 나타내는 [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7727d-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="7727d-107">제한이 경로에 대 한 반환 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7727d-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="7727d-108">[in, out] 요청 된 최대 길이 `pwzCachePath`이며 반환 될 때의 `pwzCachePath`실제 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="7727d-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7727d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7727d-109">Requirements</span></span>  
 <span data-ttu-id="7727d-110">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7727d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7727d-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7727d-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7727d-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7727d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7727d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="7727d-113">See also</span></span>

- [<span data-ttu-id="7727d-114">ASM_CACHE_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="7727d-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="7727d-115">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="7727d-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
