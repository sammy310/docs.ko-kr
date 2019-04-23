---
title: CorDebugExceptionCallbackType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91b09be04499396a2229962fd592f29cb8bc8d04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155560"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="b6226-102">CorDebugExceptionCallbackType 열거형</span><span class="sxs-lookup"><span data-stu-id="b6226-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="b6226-103">수행 되는 콜백의 형식을 나타냅니다는 [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="b6226-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6226-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6226-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="b6226-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b6226-105">Members</span></span>  
  
|<span data-ttu-id="b6226-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b6226-106">Member</span></span>|<span data-ttu-id="b6226-107">설명</span><span class="sxs-lookup"><span data-stu-id="b6226-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="b6226-108">예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6226-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="b6226-109">예외 종료 프로세스가 사용자 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6226-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="b6226-110">찾을 예외 종료 프로세스가 `catch` 사용자 코드에서 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6226-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="b6226-111">예외가 처리 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b6226-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6226-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6226-112">Requirements</span></span>  
 <span data-ttu-id="b6226-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6226-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6226-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6226-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6226-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6226-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6226-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6226-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6226-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6226-117">See also</span></span>

- [<span data-ttu-id="b6226-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="b6226-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
