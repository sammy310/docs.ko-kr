---
description: LogSwitchCallReason 열거형에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 46c457ee4c12fe9a73796aa7b7a5f599d90c9c6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800614"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="84020-103">LogSwitchCallReason 열거형</span><span class="sxs-lookup"><span data-stu-id="84020-103">LogSwitchCallReason Enumeration</span></span>

<span data-ttu-id="84020-104">디버깅/추적 스위치에 대해 수행된 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84020-104">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84020-105">구문</span><span class="sxs-lookup"><span data-stu-id="84020-105">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="84020-106">구성원</span><span class="sxs-lookup"><span data-stu-id="84020-106">Members</span></span>  
  
|<span data-ttu-id="84020-107">멤버</span><span class="sxs-lookup"><span data-stu-id="84020-107">Member</span></span>|<span data-ttu-id="84020-108">설명</span><span class="sxs-lookup"><span data-stu-id="84020-108">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="84020-109">디버깅/추적 스위치를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="84020-109">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="84020-110">디버깅/추적 스위치가 수정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="84020-110">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="84020-111">디버깅/추적 스위치가 삭제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="84020-111">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84020-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84020-112">Requirements</span></span>  

 <span data-ttu-id="84020-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84020-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84020-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84020-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84020-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84020-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84020-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84020-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84020-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84020-117">See also</span></span>

- [<span data-ttu-id="84020-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="84020-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
