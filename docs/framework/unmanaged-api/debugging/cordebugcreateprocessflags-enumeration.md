---
description: '다음에 대 한 자세한 정보: CorDebugCreateProcessFlags 열거형'
title: CorDebugCreateProcessFlags 열거형
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
ms.openlocfilehash: 29363510c83873c7f367079857809c165bc55b1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801737"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="3a78a-103">CorDebugCreateProcessFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="3a78a-103">CorDebugCreateProcessFlags Enumeration</span></span>

<span data-ttu-id="3a78a-104">[ICorDebug:: CreateProcess](icordebug-createprocess-method.md) 메서드 호출에 사용할 수 있는 추가 디버깅 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a78a-104">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a78a-105">구문</span><span class="sxs-lookup"><span data-stu-id="3a78a-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3a78a-106">구성원</span><span class="sxs-lookup"><span data-stu-id="3a78a-106">Members</span></span>  
  
|<span data-ttu-id="3a78a-107">멤버</span><span class="sxs-lookup"><span data-stu-id="3a78a-107">Member</span></span>|<span data-ttu-id="3a78a-108">설명</span><span class="sxs-lookup"><span data-stu-id="3a78a-108">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="3a78a-109">특별 한 옵션은 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a78a-109">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a78a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a78a-110">Requirements</span></span>  

 <span data-ttu-id="3a78a-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a78a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a78a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a78a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a78a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a78a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a78a-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a78a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a78a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a78a-115">See also</span></span>

- [<span data-ttu-id="3a78a-116">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="3a78a-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
