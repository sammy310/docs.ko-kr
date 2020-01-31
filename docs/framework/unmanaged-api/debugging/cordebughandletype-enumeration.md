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
ms.openlocfilehash: 15572037940f7c45ec5dcb7e34599756e15fd3bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793906"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="16e3a-102">CorDebugHandleType 열거형</span><span class="sxs-lookup"><span data-stu-id="16e3a-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="16e3a-103">핸들 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16e3a-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16e3a-104">구문</span><span class="sxs-lookup"><span data-stu-id="16e3a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="16e3a-105">Members</span><span class="sxs-lookup"><span data-stu-id="16e3a-105">Members</span></span>  
  
|<span data-ttu-id="16e3a-106">Member</span><span class="sxs-lookup"><span data-stu-id="16e3a-106">Member</span></span>|<span data-ttu-id="16e3a-107">설명</span><span class="sxs-lookup"><span data-stu-id="16e3a-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="16e3a-108">핸들이 강력 하므로 가비지 수집에 의해 개체가 회수 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16e3a-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="16e3a-109">핸들은 weak 이며 가비지 수집에 의해 개체가 회수 되는 것을 방지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16e3a-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="16e3a-110">개체를 수집 하면 핸들이 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e3a-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16e3a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16e3a-111">Requirements</span></span>  
 <span data-ttu-id="16e3a-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16e3a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16e3a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16e3a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16e3a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16e3a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16e3a-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16e3a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e3a-116">참조</span><span class="sxs-lookup"><span data-stu-id="16e3a-116">See also</span></span>

- [<span data-ttu-id="16e3a-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="16e3a-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
