---
description: '자세히 알아보기: CorDebugExceptionUnwindCallbackType 열거형'
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
ms.openlocfilehash: 3e12cffcdf1eb921330f658215c52501dce83eff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747025"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="6b9bb-103">CorDebugExceptionUnwindCallbackType 열거형</span><span class="sxs-lookup"><span data-stu-id="6b9bb-103">CorDebugExceptionUnwindCallbackType Enumeration</span></span>

<span data-ttu-id="6b9bb-104">해제 단계 중에 콜백에서 신호를 보내는 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6b9bb-104">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b9bb-105">구문</span><span class="sxs-lookup"><span data-stu-id="6b9bb-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="6b9bb-106">구성원</span><span class="sxs-lookup"><span data-stu-id="6b9bb-106">Members</span></span>  
  
|<span data-ttu-id="6b9bb-107">멤버</span><span class="sxs-lookup"><span data-stu-id="6b9bb-107">Member</span></span>|<span data-ttu-id="6b9bb-108">설명</span><span class="sxs-lookup"><span data-stu-id="6b9bb-108">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="6b9bb-109">해제 프로세스의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="6b9bb-109">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="6b9bb-110">예외가 가로채기 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9bb-110">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b9bb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b9bb-111">Requirements</span></span>  

 <span data-ttu-id="6b9bb-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b9bb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b9bb-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b9bb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b9bb-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b9bb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b9bb-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b9bb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b9bb-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b9bb-116">See also</span></span>

- [<span data-ttu-id="6b9bb-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="6b9bb-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
