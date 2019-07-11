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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193f5ffe96e89a00bed8a3c88ee346ba3ea9f2b4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740024"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="7865f-102">CorDebugGenerationTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="7865f-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="7865f-103">관리되는 힙에 대한 메모리 영역 생성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7865f-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7865f-104">구문</span><span class="sxs-lookup"><span data-stu-id="7865f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="7865f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7865f-105">Members</span></span>  
  
|<span data-ttu-id="7865f-106">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="7865f-106">Member name</span></span>|<span data-ttu-id="7865f-107">Description</span><span class="sxs-lookup"><span data-stu-id="7865f-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="7865f-108">0세대.</span><span class="sxs-lookup"><span data-stu-id="7865f-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="7865f-109">1세대.</span><span class="sxs-lookup"><span data-stu-id="7865f-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="7865f-110">2세대.</span><span class="sxs-lookup"><span data-stu-id="7865f-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="7865f-111">대형 개체 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="7865f-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7865f-112">설명</span><span class="sxs-lookup"><span data-stu-id="7865f-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7865f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7865f-113">Requirements</span></span>  
 <span data-ttu-id="7865f-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7865f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7865f-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7865f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7865f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7865f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7865f-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7865f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7865f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="7865f-118">See also</span></span>

- [<span data-ttu-id="7865f-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="7865f-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
