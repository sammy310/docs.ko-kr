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
ms.openlocfilehash: 92366190c769344b41923cbb25ed4b04afceaae9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778662"
---
# <a name="getcachepath-function"></a><span data-ttu-id="a4d18-102">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="a4d18-102">GetCachePath Function</span></span>
<span data-ttu-id="a4d18-103">지정된 된 플래그를 사용 하 여 캐시 된 어셈블리에 경로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4d18-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d18-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4d18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4d18-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4d18-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="a4d18-106">[in] [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) 캐시 된 어셈블리의 소스를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a4d18-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="a4d18-107">[out] 경로에 반환 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4d18-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="a4d18-108">[out에서] 요청한 최대 길이인 `pwzCachePath`, 및의 실제 길이가 반환 될 때 `pwzCachePath`합니다.</span><span class="sxs-lookup"><span data-stu-id="a4d18-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4d18-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4d18-109">Requirements</span></span>  
 <span data-ttu-id="a4d18-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4d18-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d18-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a4d18-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a4d18-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4d18-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d18-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a4d18-113">See also</span></span>

- [<span data-ttu-id="a4d18-114">ASM_CACHE_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="a4d18-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [<span data-ttu-id="a4d18-115">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="a4d18-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
