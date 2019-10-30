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
ms.openlocfilehash: 13e1468ef5a48f18910c1f8082cdd7c4849da14a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132692"
---
# <a name="getcachepath-function"></a><span data-ttu-id="6de96-102">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="6de96-102">GetCachePath Function</span></span>
<span data-ttu-id="6de96-103">지정 된 플래그를 사용 하 여 캐시 된 어셈블리에 대 한 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6de96-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de96-104">구문</span><span class="sxs-lookup"><span data-stu-id="6de96-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6de96-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6de96-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="6de96-106">진행 캐시 된 어셈블리의 소스를 나타내는 [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6de96-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="6de96-107">제한이 경로에 대 한 반환 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6de96-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="6de96-108">[in, out] 요청 된 최대 `pwzCachePath`길이 이며 반환 시 `pwzCachePath`의 실제 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="6de96-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de96-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6de96-109">Requirements</span></span>  
 <span data-ttu-id="6de96-110">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6de96-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de96-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6de96-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6de96-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de96-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de96-113">참조</span><span class="sxs-lookup"><span data-stu-id="6de96-113">See also</span></span>

- [<span data-ttu-id="6de96-114">ASM_CACHE_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="6de96-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="6de96-115">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6de96-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
