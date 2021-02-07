---
description: '자세히 알아보기: CorDebugGenerationTypes 열거형'
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
ms.openlocfilehash: f86b2bc9bf947c6b285c50678f46494005bb5537
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662132"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="df463-103">CorDebugGenerationTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="df463-103">CorDebugGenerationTypes Enumeration</span></span>

<span data-ttu-id="df463-104">관리되는 힙에 대한 메모리 영역 생성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df463-104">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df463-105">구문</span><span class="sxs-lookup"><span data-stu-id="df463-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="df463-106">구성원</span><span class="sxs-lookup"><span data-stu-id="df463-106">Members</span></span>  
  
|<span data-ttu-id="df463-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="df463-107">Member name</span></span>|<span data-ttu-id="df463-108">설명</span><span class="sxs-lookup"><span data-stu-id="df463-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="df463-109">0세대.</span><span class="sxs-lookup"><span data-stu-id="df463-109">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="df463-110">1세대</span><span class="sxs-lookup"><span data-stu-id="df463-110">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="df463-111">2세대.</span><span class="sxs-lookup"><span data-stu-id="df463-111">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="df463-112">Large object heap입니다.</span><span class="sxs-lookup"><span data-stu-id="df463-112">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df463-113">설명</span><span class="sxs-lookup"><span data-stu-id="df463-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df463-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df463-114">Requirements</span></span>  

 <span data-ttu-id="df463-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df463-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df463-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df463-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df463-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df463-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df463-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df463-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df463-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df463-119">See also</span></span>

- [<span data-ttu-id="df463-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="df463-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
