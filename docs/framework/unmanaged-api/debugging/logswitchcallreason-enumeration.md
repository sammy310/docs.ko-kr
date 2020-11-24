---
title: LogSwitchCallReason 열거형
ms.date: 03/30/2017
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
ms.openlocfilehash: dfb34595530a47b74762610f5824b68ea00a8a69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671943"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="55505-102">LogSwitchCallReason 열거형</span><span class="sxs-lookup"><span data-stu-id="55505-102">LogSwitchCallReason Enumeration</span></span>

<span data-ttu-id="55505-103">디버깅/추적 스위치에 대해 수행된 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55505-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55505-104">구문</span><span class="sxs-lookup"><span data-stu-id="55505-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="55505-105">멤버</span><span class="sxs-lookup"><span data-stu-id="55505-105">Members</span></span>  
  
|<span data-ttu-id="55505-106">멤버</span><span class="sxs-lookup"><span data-stu-id="55505-106">Member</span></span>|<span data-ttu-id="55505-107">설명</span><span class="sxs-lookup"><span data-stu-id="55505-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="55505-108">디버깅/추적 스위치를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="55505-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="55505-109">디버깅/추적 스위치가 수정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55505-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="55505-110">디버깅/추적 스위치가 삭제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55505-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55505-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55505-111">Requirements</span></span>  

 <span data-ttu-id="55505-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55505-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55505-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55505-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55505-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55505-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55505-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55505-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55505-116">참조</span><span class="sxs-lookup"><span data-stu-id="55505-116">See also</span></span>

- [<span data-ttu-id="55505-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="55505-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
