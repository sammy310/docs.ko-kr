---
title: CorDebugGCType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe8be6a7c18fff54825f981672f0f640bb60c35c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482212"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="f07e5-102">CorDebugGCType 열거형</span><span class="sxs-lookup"><span data-stu-id="f07e5-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="f07e5-103">가비지 수집기가 실행되고 있는 위치(워크스테이션 또는 서버)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f07e5-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f07e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="f07e5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f07e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f07e5-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="f07e5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f07e5-106">Members</span></span>  
  
|<span data-ttu-id="f07e5-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="f07e5-107">Member name</span></span>|<span data-ttu-id="f07e5-108">설명</span><span class="sxs-lookup"><span data-stu-id="f07e5-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="f07e5-109">가비지 수집기는 워크스테이션에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07e5-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="f07e5-110">가비지 수집기는 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07e5-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f07e5-111">설명</span><span class="sxs-lookup"><span data-stu-id="f07e5-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f07e5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f07e5-112">Requirements</span></span>  
 <span data-ttu-id="f07e5-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f07e5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f07e5-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f07e5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f07e5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f07e5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f07e5-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f07e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07e5-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f07e5-117">See also</span></span>
- [<span data-ttu-id="f07e5-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="f07e5-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
