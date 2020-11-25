---
title: CorDebugGuidToTypeMapping 구조체
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
ms.openlocfilehash: 859853521b741f42f1de7921de813941d2501173
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729098"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="ae551-102">CorDebugGuidToTypeMapping 구조체</span><span class="sxs-lookup"><span data-stu-id="ae551-102">CorDebugGuidToTypeMapping Structure</span></span>

<span data-ttu-id="ae551-103">Windows 런타임 GUID를 해당 ICorDebugType 개체에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ae551-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae551-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae551-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="ae551-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ae551-105">Members</span></span>  
  
|<span data-ttu-id="ae551-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ae551-106">Member</span></span>|<span data-ttu-id="ae551-107">설명</span><span class="sxs-lookup"><span data-stu-id="ae551-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="ae551-108">캐시 된 Windows 런타임 형식의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae551-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="ae551-109">캐시 된 형식에 대 한 정보를 제공 하는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae551-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae551-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae551-110">Requirements</span></span>  

 <span data-ttu-id="ae551-111">**플랫폼:** Windows 런타임.</span><span class="sxs-lookup"><span data-stu-id="ae551-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="ae551-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae551-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae551-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae551-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae551-114">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae551-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae551-115">참조</span><span class="sxs-lookup"><span data-stu-id="ae551-115">See also</span></span>

- [<span data-ttu-id="ae551-116">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="ae551-116">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="ae551-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="ae551-117">Debugging</span></span>](index.md)
