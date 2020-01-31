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
ms.openlocfilehash: 29781666c106755f96f945325e3a8953bf93b211
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790343"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="acf30-102">LogSwitchCallReason 열거형</span><span class="sxs-lookup"><span data-stu-id="acf30-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="acf30-103">디버깅/추적 스위치에 대해 수행된 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="acf30-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf30-104">구문</span><span class="sxs-lookup"><span data-stu-id="acf30-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="acf30-105">Members</span><span class="sxs-lookup"><span data-stu-id="acf30-105">Members</span></span>  
  
|<span data-ttu-id="acf30-106">Member</span><span class="sxs-lookup"><span data-stu-id="acf30-106">Member</span></span>|<span data-ttu-id="acf30-107">설명</span><span class="sxs-lookup"><span data-stu-id="acf30-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="acf30-108">디버깅/추적 스위치를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="acf30-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="acf30-109">디버깅/추적 스위치가 수정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="acf30-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="acf30-110">디버깅/추적 스위치가 삭제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="acf30-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acf30-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="acf30-111">Requirements</span></span>  
 <span data-ttu-id="acf30-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acf30-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf30-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acf30-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acf30-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acf30-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acf30-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf30-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf30-116">참조</span><span class="sxs-lookup"><span data-stu-id="acf30-116">See also</span></span>

- [<span data-ttu-id="acf30-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="acf30-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
