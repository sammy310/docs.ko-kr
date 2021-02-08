---
description: '자세히 알아보기: CorDebugGuidToTypeMapping Structure'
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
ms.openlocfilehash: 5f6e99a17483b4fc16eb36ebb5fb5fd81380944b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801620"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="c6675-103">CorDebugGuidToTypeMapping 구조체</span><span class="sxs-lookup"><span data-stu-id="c6675-103">CorDebugGuidToTypeMapping Structure</span></span>

<span data-ttu-id="c6675-104">Windows 런타임 GUID를 해당 ICorDebugType 개체에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c6675-104">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6675-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6675-105">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="c6675-106">구성원</span><span class="sxs-lookup"><span data-stu-id="c6675-106">Members</span></span>  
  
|<span data-ttu-id="c6675-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c6675-107">Member</span></span>|<span data-ttu-id="c6675-108">설명</span><span class="sxs-lookup"><span data-stu-id="c6675-108">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="c6675-109">캐시 된 Windows 런타임 형식의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="c6675-109">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="c6675-110">캐시 된 형식에 대 한 정보를 제공 하는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6675-110">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6675-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6675-111">Requirements</span></span>  

 <span data-ttu-id="c6675-112">**플랫폼:** Windows 런타임.</span><span class="sxs-lookup"><span data-stu-id="c6675-112">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="c6675-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6675-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6675-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6675-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6675-115">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6675-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6675-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6675-116">See also</span></span>

- [<span data-ttu-id="c6675-117">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="c6675-117">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c6675-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="c6675-118">Debugging</span></span>](index.md)
