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
ms.openlocfilehash: 2d296c1778e00c4c72e860e0705994518d1481e8
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795885"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="553a3-102">CorDebugHandleType 열거형</span><span class="sxs-lookup"><span data-stu-id="553a3-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="553a3-103">핸들 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="553a3-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="553a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="553a3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="553a3-105">구성원</span><span class="sxs-lookup"><span data-stu-id="553a3-105">Members</span></span>  
  
|<span data-ttu-id="553a3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="553a3-106">Member</span></span>|<span data-ttu-id="553a3-107">설명</span><span class="sxs-lookup"><span data-stu-id="553a3-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="553a3-108">핸들이 강력 하므로 가비지 수집에 의해 개체가 회수 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="553a3-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="553a3-109">핸들은 weak 이며 가비지 수집에 의해 개체가 회수 되는 것을 방지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="553a3-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="553a3-110">개체를 수집 하면 핸들이 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="553a3-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="553a3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="553a3-111">Requirements</span></span>  
 <span data-ttu-id="553a3-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="553a3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="553a3-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="553a3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="553a3-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="553a3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="553a3-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="553a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553a3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="553a3-116">See also</span></span>

- [<span data-ttu-id="553a3-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="553a3-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
