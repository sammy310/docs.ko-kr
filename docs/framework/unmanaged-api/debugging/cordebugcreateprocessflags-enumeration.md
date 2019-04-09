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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae3ba480e208762f5a80f9f1b78dd008f02b6df4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089383"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="15861-102">CorDebugCreateProcessFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="15861-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="15861-103">에 대 한 호출에서 사용할 수 있는 추가 디버깅 옵션을 제공 합니다 [icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="15861-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15861-104">구문</span><span class="sxs-lookup"><span data-stu-id="15861-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="15861-105">멤버</span><span class="sxs-lookup"><span data-stu-id="15861-105">Members</span></span>  
  
|<span data-ttu-id="15861-106">멤버</span><span class="sxs-lookup"><span data-stu-id="15861-106">Member</span></span>|<span data-ttu-id="15861-107">설명</span><span class="sxs-lookup"><span data-stu-id="15861-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="15861-108">특별 한 옵션 없이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15861-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15861-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15861-109">Requirements</span></span>  
 <span data-ttu-id="15861-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="15861-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15861-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15861-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15861-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15861-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="15861-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="15861-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15861-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="15861-114">See also</span></span>

- [<span data-ttu-id="15861-115">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="15861-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
