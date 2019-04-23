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
ms.openlocfilehash: 9dc7093edaf12e801a1e1adc52b0be823ff92b91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079918"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="96e19-102">CorDebugGuidToTypeMapping 구조체</span><span class="sxs-lookup"><span data-stu-id="96e19-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="96e19-103">Maps는 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 해당 ICorDebugType 개체 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="96e19-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e19-104">구문</span><span class="sxs-lookup"><span data-stu-id="96e19-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="96e19-105">멤버</span><span class="sxs-lookup"><span data-stu-id="96e19-105">Members</span></span>  
  
|<span data-ttu-id="96e19-106">멤버</span><span class="sxs-lookup"><span data-stu-id="96e19-106">Member</span></span>|<span data-ttu-id="96e19-107">설명</span><span class="sxs-lookup"><span data-stu-id="96e19-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="96e19-108">캐시 된 GUID [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="96e19-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="96e19-109">캐시 된 유형에 대 한 정보를 제공 하는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96e19-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96e19-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96e19-110">Requirements</span></span>  
 <span data-ttu-id="96e19-111">**플랫폼:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="96e19-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="96e19-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96e19-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96e19-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96e19-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96e19-114">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96e19-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e19-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="96e19-115">See also</span></span>

- [<span data-ttu-id="96e19-116">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="96e19-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="96e19-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="96e19-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
