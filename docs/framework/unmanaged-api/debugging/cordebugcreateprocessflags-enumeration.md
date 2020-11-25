---
title: CorDebugCreateProcessFlags 열거형
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
ms.openlocfilehash: f6f589656a3063fc89bd276b32d0ed751fd8d2d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733401"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="7961d-102">CorDebugCreateProcessFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="7961d-102">CorDebugCreateProcessFlags Enumeration</span></span>

<span data-ttu-id="7961d-103">[ICorDebug:: CreateProcess](icordebug-createprocess-method.md) 메서드 호출에 사용할 수 있는 추가 디버깅 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7961d-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7961d-104">구문</span><span class="sxs-lookup"><span data-stu-id="7961d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="7961d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7961d-105">Members</span></span>  
  
|<span data-ttu-id="7961d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7961d-106">Member</span></span>|<span data-ttu-id="7961d-107">설명</span><span class="sxs-lookup"><span data-stu-id="7961d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="7961d-108">특별 한 옵션은 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7961d-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7961d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7961d-109">Requirements</span></span>  

 <span data-ttu-id="7961d-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7961d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7961d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7961d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7961d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7961d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7961d-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7961d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7961d-114">참조</span><span class="sxs-lookup"><span data-stu-id="7961d-114">See also</span></span>

- [<span data-ttu-id="7961d-115">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="7961d-115">Debugging Enumerations</span></span>](debugging-enumerations.md)
