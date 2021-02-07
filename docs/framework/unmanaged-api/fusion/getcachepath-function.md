---
description: '자세한 정보: GetCachePath 함수'
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
ms.openlocfilehash: 4f5045d4110ca9aae33ef54eb85a2146f855e6c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761044"
---
# <a name="getcachepath-function"></a><span data-ttu-id="dc19c-103">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="dc19c-103">GetCachePath Function</span></span>

<span data-ttu-id="dc19c-104">지정 된 플래그를 사용 하 여 캐시 된 어셈블리에 대 한 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dc19c-104">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc19c-105">구문</span><span class="sxs-lookup"><span data-stu-id="dc19c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc19c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc19c-106">Parameters</span></span>  

 `dwCacheFlags`  
 <span data-ttu-id="dc19c-107">진행 캐시 된 어셈블리의 소스를 나타내는 [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dc19c-107">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="dc19c-108">제한이 경로에 대 한 반환 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc19c-108">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="dc19c-109">[in, out] 요청 된 최대 길이 `pwzCachePath` 이며 반환 될 때의 실제 길이입니다 `pwzCachePath` .</span><span class="sxs-lookup"><span data-stu-id="dc19c-109">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc19c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc19c-110">Requirements</span></span>  

 <span data-ttu-id="dc19c-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc19c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc19c-112">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="dc19c-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dc19c-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc19c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc19c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc19c-114">See also</span></span>

- [<span data-ttu-id="dc19c-115">ASM_CACHE_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="dc19c-115">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="dc19c-116">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="dc19c-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
