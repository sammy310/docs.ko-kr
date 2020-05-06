---
title: CorDebugExceptionFlags 열거형
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
ms.openlocfilehash: 45de821dd52f7e153fc79ffde056ed959c654fce
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795952"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="8d2dc-102">CorDebugExceptionFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="8d2dc-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="8d2dc-103">예외에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2dc-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d2dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="8d2dc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8d2dc-105">구성원</span><span class="sxs-lookup"><span data-stu-id="8d2dc-105">Members</span></span>  
  
|<span data-ttu-id="8d2dc-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8d2dc-106">Member</span></span>|<span data-ttu-id="8d2dc-107">설명</span><span class="sxs-lookup"><span data-stu-id="8d2dc-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="8d2dc-108">예외가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d2dc-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="8d2dc-109">예외를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d2dc-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="8d2dc-110">시간상 디버거가 아직 예외를 가로챌 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d2dc-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="8d2dc-111">예를 들어 현재 콜백 아래에 관리 코드가 없거나 예외 이벤트가 JIT(Just-In-Time) 연결에서 발생한 경우에는 예외를 가로챌 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d2dc-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d2dc-112">설명</span><span class="sxs-lookup"><span data-stu-id="8d2dc-112">Remarks</span></span>  
 <span data-ttu-id="8d2dc-113">이후 버전에서는 이 열거형에 대해 새 값이 추가될 수 있으므로 예기치 않은 값에 대해 `CorDebugExceptionFlags`를 사용하는 코드를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2dc-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d2dc-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d2dc-114">Requirements</span></span>  
 <span data-ttu-id="8d2dc-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d2dc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d2dc-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d2dc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d2dc-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d2dc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d2dc-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d2dc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d2dc-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d2dc-119">See also</span></span>

- [<span data-ttu-id="8d2dc-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="8d2dc-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
