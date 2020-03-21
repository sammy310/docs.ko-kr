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
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179300"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="ad20b-102">COR_IL_MAP 구조체</span><span class="sxs-lookup"><span data-stu-id="ad20b-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="ad20b-103">함수의 상대 오프셋 변경 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad20b-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad20b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="ad20b-105">구성원</span><span class="sxs-lookup"><span data-stu-id="ad20b-105">Members</span></span>  
  
|<span data-ttu-id="ad20b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ad20b-106">Member</span></span>|<span data-ttu-id="ad20b-107">Description</span><span class="sxs-lookup"><span data-stu-id="ad20b-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="ad20b-108">이전 Microsoft 중간 언어(MSIL)는 함수의 시작 부분을 기준으로 오프셋됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="ad20b-109">함수의 시작 부분을 기준으로 새 MSIL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="ad20b-110">`true`매핑이 정확하다고 알려져 있는 경우; 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="ad20b-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad20b-111">설명</span><span class="sxs-lookup"><span data-stu-id="ad20b-111">Remarks</span></span>  
 <span data-ttu-id="ad20b-112">맵의 형식은 다음과 같습니다: 디버거는 수정되지 않은 원래 MSIL 코드 내에서 MSIL 오프셋을 참조한다고 `oldOffset` 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="ad20b-113">매개 `newOffset` 변수는 계측된 새 코드 내에서 해당 MSIL 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="ad20b-114">스테핑이 제대로 작동하려면 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="ad20b-115">맵은 오름차순으로 정렬해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="ad20b-116">계측된 MSIL 코드는 순서를 바운지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="ad20b-117">원래 MSIL 코드를 제거하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="ad20b-118">맵에는 프로그램 데이터베이스(PDB) 파일의 모든 시퀀스 지점을 매핑하는 항목이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="ad20b-119">맵은 누락된 항목을 보간하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="ad20b-120">다음 예제에서는 맵과 그 결과를 보여 주며 그 결과를 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="ad20b-121">지도:</span><span class="sxs-lookup"><span data-stu-id="ad20b-121">Map:</span></span>  
  
- <span data-ttu-id="ad20b-122">0 이전 오프셋, 0 개의 새 오프셋</span><span class="sxs-lookup"><span data-stu-id="ad20b-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="ad20b-123">5 이전 오프셋, 10 개의 새 오프셋</span><span class="sxs-lookup"><span data-stu-id="ad20b-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="ad20b-124">9 이전 오프셋, 20 개의 새 오프셋</span><span class="sxs-lookup"><span data-stu-id="ad20b-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="ad20b-125">결과:</span><span class="sxs-lookup"><span data-stu-id="ad20b-125">Results:</span></span>  
  
- <span data-ttu-id="ad20b-126">0, 1, 2, 3 또는 4의 이전 오프셋은 0의 새 오프셋에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="ad20b-127">5, 6, 7 또는 8의 이전 오프셋은 새 오프셋 10에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="ad20b-128">9 이상의 이전 오프셋은 새 오프셋 20에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="ad20b-129">0, 1, 2, 3, 4, 5, 6, 7, 8 또는 9의 새 오프셋이 이전 오프셋 0에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="ad20b-130">10, 11, 12, 13, 14, 15, 16, 17, 18 또는 19의 새 오프셋이 이전 오프셋 5에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="ad20b-131">20 이상의 새 오프셋은 이전 오프셋 9에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad20b-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad20b-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad20b-132">Requirements</span></span>  
 <span data-ttu-id="ad20b-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad20b-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad20b-134">**헤더:** 코르데버그.idl, 코르프로프.아이들</span><span class="sxs-lookup"><span data-stu-id="ad20b-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="ad20b-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad20b-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad20b-136">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad20b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad20b-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad20b-137">See also</span></span>

- [<span data-ttu-id="ad20b-138">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="ad20b-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="ad20b-139">디버깅</span><span class="sxs-lookup"><span data-stu-id="ad20b-139">Debugging</span></span>](index.md)
