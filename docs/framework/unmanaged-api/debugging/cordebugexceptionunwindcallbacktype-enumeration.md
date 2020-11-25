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
ms.openlocfilehash: 30de1448a7d1452e1e9049411010e7f43d13eb70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712640"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="1ee9e-102">CorDebugExceptionUnwindCallbackType 열거형</span><span class="sxs-lookup"><span data-stu-id="1ee9e-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>

<span data-ttu-id="1ee9e-103">해제 단계 중에 콜백에서 신호를 보내는 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1ee9e-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ee9e-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ee9e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="1ee9e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1ee9e-105">Members</span></span>  
  
|<span data-ttu-id="1ee9e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1ee9e-106">Member</span></span>|<span data-ttu-id="1ee9e-107">설명</span><span class="sxs-lookup"><span data-stu-id="1ee9e-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="1ee9e-108">해제 프로세스의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="1ee9e-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="1ee9e-109">예외가 가로채기 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee9e-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ee9e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ee9e-110">Requirements</span></span>  

 <span data-ttu-id="1ee9e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ee9e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ee9e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ee9e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ee9e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ee9e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ee9e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ee9e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee9e-115">참조</span><span class="sxs-lookup"><span data-stu-id="1ee9e-115">See also</span></span>

- [<span data-ttu-id="1ee9e-116">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="1ee9e-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
