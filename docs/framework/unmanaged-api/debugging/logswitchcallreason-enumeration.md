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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7eadb595eb62b4f1a9dcc888225cbb7454119c7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198493"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="4b755-102">LogSwitchCallReason 열거형</span><span class="sxs-lookup"><span data-stu-id="4b755-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="4b755-103">디버깅/추적 스위치에 대해 수행된 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b755-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b755-104">구문</span><span class="sxs-lookup"><span data-stu-id="4b755-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="4b755-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4b755-105">Members</span></span>  
  
|<span data-ttu-id="4b755-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4b755-106">Member</span></span>|<span data-ttu-id="4b755-107">설명</span><span class="sxs-lookup"><span data-stu-id="4b755-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="4b755-108">디버깅/추적 스위치 생성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4b755-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="4b755-109">디버깅/추적 스위치를 수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4b755-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="4b755-110">디버깅/추적 스위치를 삭제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4b755-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4b755-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b755-111">Requirements</span></span>  
 <span data-ttu-id="4b755-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b755-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b755-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b755-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b755-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b755-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4b755-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="4b755-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4b755-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="4b755-116">See also</span></span>

- [<span data-ttu-id="4b755-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="4b755-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
