---
title: CorDebugGenerationTypes 열거형
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
ms.openlocfilehash: 189a276b4228038ab1d70620ce3a4a0f4342b245
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712523"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="94fd4-102">CorDebugGenerationTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="94fd4-102">CorDebugGenerationTypes Enumeration</span></span>

<span data-ttu-id="94fd4-103">관리되는 힙에 대한 메모리 영역 생성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94fd4-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94fd4-104">구문</span><span class="sxs-lookup"><span data-stu-id="94fd4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="94fd4-105">멤버</span><span class="sxs-lookup"><span data-stu-id="94fd4-105">Members</span></span>  
  
|<span data-ttu-id="94fd4-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="94fd4-106">Member name</span></span>|<span data-ttu-id="94fd4-107">설명</span><span class="sxs-lookup"><span data-stu-id="94fd4-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="94fd4-108">0세대.</span><span class="sxs-lookup"><span data-stu-id="94fd4-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="94fd4-109">1세대</span><span class="sxs-lookup"><span data-stu-id="94fd4-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="94fd4-110">2세대.</span><span class="sxs-lookup"><span data-stu-id="94fd4-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="94fd4-111">Large object heap입니다.</span><span class="sxs-lookup"><span data-stu-id="94fd4-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94fd4-112">설명</span><span class="sxs-lookup"><span data-stu-id="94fd4-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94fd4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94fd4-113">Requirements</span></span>  

 <span data-ttu-id="94fd4-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94fd4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94fd4-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94fd4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94fd4-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94fd4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94fd4-117">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fd4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fd4-118">참조</span><span class="sxs-lookup"><span data-stu-id="94fd4-118">See also</span></span>

- [<span data-ttu-id="94fd4-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="94fd4-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
