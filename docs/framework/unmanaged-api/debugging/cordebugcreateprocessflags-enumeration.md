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
ms.openlocfilehash: c0e4c43ac18b5e214d38dd7a57452a3871e4b43d
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796030"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="63fe8-102">CorDebugCreateProcessFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="63fe8-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="63fe8-103">[ICorDebug:: CreateProcess](icordebug-createprocess-method.md) 메서드 호출에 사용할 수 있는 추가 디버깅 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="63fe8-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63fe8-104">구문</span><span class="sxs-lookup"><span data-stu-id="63fe8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="63fe8-105">구성원</span><span class="sxs-lookup"><span data-stu-id="63fe8-105">Members</span></span>  
  
|<span data-ttu-id="63fe8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="63fe8-106">Member</span></span>|<span data-ttu-id="63fe8-107">설명</span><span class="sxs-lookup"><span data-stu-id="63fe8-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="63fe8-108">특별 한 옵션은 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63fe8-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63fe8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63fe8-109">Requirements</span></span>  
 <span data-ttu-id="63fe8-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63fe8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63fe8-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63fe8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63fe8-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63fe8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63fe8-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63fe8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fe8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63fe8-114">See also</span></span>

- [<span data-ttu-id="63fe8-115">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="63fe8-115">Debugging Enumerations</span></span>](debugging-enumerations.md)
