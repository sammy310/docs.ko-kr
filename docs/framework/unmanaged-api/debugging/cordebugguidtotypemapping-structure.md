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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38e1b19d6340f559e6f8b7e0f7bc042a10df16c3
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025994"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="4cc77-102">CorDebugGuidToTypeMapping 구조체</span><span class="sxs-lookup"><span data-stu-id="4cc77-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="4cc77-103">Windows 런타임 GUID 해당 ICorDebugType 개체에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cc77-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc77-104">구문</span><span class="sxs-lookup"><span data-stu-id="4cc77-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="4cc77-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4cc77-105">Members</span></span>  
  
|<span data-ttu-id="4cc77-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4cc77-106">Member</span></span>|<span data-ttu-id="4cc77-107">설명</span><span class="sxs-lookup"><span data-stu-id="4cc77-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="4cc77-108">캐시 된 Windows 런타임 형식의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="4cc77-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="4cc77-109">캐시 된 유형에 대 한 정보를 제공 하는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4cc77-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cc77-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cc77-110">Requirements</span></span>  
 <span data-ttu-id="4cc77-111">**플랫폼:** Windows 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="4cc77-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="4cc77-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cc77-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cc77-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cc77-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cc77-114">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cc77-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc77-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="4cc77-115">See also</span></span>

- [<span data-ttu-id="4cc77-116">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="4cc77-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="4cc77-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="4cc77-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
