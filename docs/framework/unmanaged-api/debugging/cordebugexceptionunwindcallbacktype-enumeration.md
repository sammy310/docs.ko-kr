---
title: CorDebugExceptionUnwindCallbackType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408e72eeaa1dac83c45488d186425f30c6043280
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155625"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="fce5e-102">CorDebugExceptionUnwindCallbackType 열거형</span><span class="sxs-lookup"><span data-stu-id="fce5e-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="fce5e-103">해제 단계 중에 콜백에서 신호를 보내는 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fce5e-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fce5e-104">구문</span><span class="sxs-lookup"><span data-stu-id="fce5e-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="fce5e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="fce5e-105">Members</span></span>  
  
|<span data-ttu-id="fce5e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="fce5e-106">Member</span></span>|<span data-ttu-id="fce5e-107">설명</span><span class="sxs-lookup"><span data-stu-id="fce5e-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="fce5e-108">시작 해제 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="fce5e-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="fce5e-109">예외를 가로 챘 습니다.</span><span class="sxs-lookup"><span data-stu-id="fce5e-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fce5e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fce5e-110">Requirements</span></span>  
 <span data-ttu-id="fce5e-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fce5e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fce5e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fce5e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fce5e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fce5e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fce5e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fce5e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce5e-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fce5e-115">See also</span></span>

- [<span data-ttu-id="fce5e-116">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="fce5e-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
