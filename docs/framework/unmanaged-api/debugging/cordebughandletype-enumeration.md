---
title: CorDebugHandleType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513fc93bdac71e2a3ba59ebb53fdde44f1659af5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220463"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="30d18-102">CorDebugHandleType 열거형</span><span class="sxs-lookup"><span data-stu-id="30d18-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="30d18-103">핸들 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="30d18-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30d18-104">구문</span><span class="sxs-lookup"><span data-stu-id="30d18-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="30d18-105">멤버</span><span class="sxs-lookup"><span data-stu-id="30d18-105">Members</span></span>  
  
|<span data-ttu-id="30d18-106">멤버</span><span class="sxs-lookup"><span data-stu-id="30d18-106">Member</span></span>|<span data-ttu-id="30d18-107">설명</span><span class="sxs-lookup"><span data-stu-id="30d18-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="30d18-108">핸들이 강력한 개체에서 가비지 수집에 의해 회수 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d18-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="30d18-109">핸들이 약한는 하지 않는 개체에서 가비지 수집에 의해 회수 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d18-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="30d18-110">개체는 수집 하는 경우 핸들이 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30d18-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30d18-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30d18-111">Requirements</span></span>  
 <span data-ttu-id="30d18-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="30d18-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30d18-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30d18-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30d18-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30d18-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="30d18-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="30d18-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="30d18-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="30d18-116">See also</span></span>

- [<span data-ttu-id="30d18-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="30d18-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
