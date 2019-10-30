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
ms.openlocfilehash: d28f6eab5390194a4089cbbaf1f586c3f53a7db5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132250"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="0c12e-102">CorDebugCreateProcessFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="0c12e-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="0c12e-103">[ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) 메서드 호출에 사용할 수 있는 추가 디버깅 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c12e-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c12e-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c12e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0c12e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0c12e-105">Members</span></span>  
  
|<span data-ttu-id="0c12e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0c12e-106">Member</span></span>|<span data-ttu-id="0c12e-107">설명</span><span class="sxs-lookup"><span data-stu-id="0c12e-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="0c12e-108">특별 한 옵션은 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c12e-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c12e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c12e-109">Requirements</span></span>  
 <span data-ttu-id="0c12e-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c12e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c12e-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c12e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c12e-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c12e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c12e-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c12e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c12e-114">참조</span><span class="sxs-lookup"><span data-stu-id="0c12e-114">See also</span></span>

- [<span data-ttu-id="0c12e-115">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="0c12e-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
