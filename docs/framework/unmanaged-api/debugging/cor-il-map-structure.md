---
title: COR_IL_MAP 구조체
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
ms.openlocfilehash: fb6b5d43e60b52c867535c42d59a098ef3c959bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726387"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="59bb7-102">COR_IL_MAP 구조체</span><span class="sxs-lookup"><span data-stu-id="59bb7-102">COR_IL_MAP Structure</span></span>

<span data-ttu-id="59bb7-103">함수의 상대 오프셋 변경 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59bb7-104">구문</span><span class="sxs-lookup"><span data-stu-id="59bb7-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="59bb7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="59bb7-105">Members</span></span>  
  
|<span data-ttu-id="59bb7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="59bb7-106">Member</span></span>|<span data-ttu-id="59bb7-107">설명</span><span class="sxs-lookup"><span data-stu-id="59bb7-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="59bb7-108">함수의 시작 부분을 기준으로 하는 이전 MSIL (Microsoft 중간 언어) 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="59bb7-109">함수의 시작 부분을 기준으로 하는 새 MSIL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="59bb7-110">`true` 매핑이 정확한 것으로 알려져 있으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59bb7-111">설명</span><span class="sxs-lookup"><span data-stu-id="59bb7-111">Remarks</span></span>  

 <span data-ttu-id="59bb7-112">맵의 형식은 다음과 같습니다. 디버거는가 수정 되지 않은 `oldOffset` 원래 msil 코드 내에서 msil 오프셋을 참조 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="59bb7-113">`newOffset`매개 변수는 계측 된 새 코드 내에서 해당 MSIL 오프셋을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="59bb7-114">단계별 실행이 제대로 작동 하려면 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="59bb7-115">맵은 오름차순으로 정렬 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="59bb7-116">계측 된 MSIL 코드는 다시 정렬 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="59bb7-117">원래 MSIL 코드는 제거 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="59bb7-118">맵에는 PDB (프로그램 데이터베이스) 파일의 모든 시퀀스 위치를 매핑하는 항목이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="59bb7-119">지도는 누락 된 항목을 보간 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="59bb7-120">다음 예에서는 맵과 해당 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="59bb7-121">매핑할</span><span class="sxs-lookup"><span data-stu-id="59bb7-121">Map:</span></span>  
  
- <span data-ttu-id="59bb7-122">0 이전 오프셋, 0 새 오프셋</span><span class="sxs-lookup"><span data-stu-id="59bb7-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="59bb7-123">5 이전 오프셋, 10 개의 새 오프셋</span><span class="sxs-lookup"><span data-stu-id="59bb7-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="59bb7-124">9 이전 오프셋, 20 개의 새 오프셋</span><span class="sxs-lookup"><span data-stu-id="59bb7-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="59bb7-125">결과:</span><span class="sxs-lookup"><span data-stu-id="59bb7-125">Results:</span></span>  
  
- <span data-ttu-id="59bb7-126">0, 1, 2, 3 또는 4의 이전 오프셋은 0의 새 오프셋에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="59bb7-127">5, 6, 7 또는 8의 이전 오프셋은 새 오프셋 10에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="59bb7-128">이전 오프셋 9 이상은 새 오프셋 20에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="59bb7-129">0, 1, 2, 3, 4, 5, 6, 7, 8 또는 9의 새 오프셋은 이전 오프셋 0에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="59bb7-130">새 오프셋 10, 11, 12, 13, 14, 15, 16, 17, 18 또는 19는 이전 오프셋 5에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="59bb7-131">새 오프셋 20 이상은 이전 오프셋 9에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="59bb7-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59bb7-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59bb7-132">Requirements</span></span>  

 <span data-ttu-id="59bb7-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59bb7-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59bb7-134">**헤더:** CorDebug .idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="59bb7-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="59bb7-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59bb7-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59bb7-136">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59bb7-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59bb7-137">참조</span><span class="sxs-lookup"><span data-stu-id="59bb7-137">See also</span></span>

- [<span data-ttu-id="59bb7-138">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="59bb7-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="59bb7-139">디버깅</span><span class="sxs-lookup"><span data-stu-id="59bb7-139">Debugging</span></span>](index.md)
