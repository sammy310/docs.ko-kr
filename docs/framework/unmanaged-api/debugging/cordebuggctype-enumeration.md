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
ms.openlocfilehash: 315d6dd522f3c6be2d36b1eb411d9f471350df60
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182925"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="d34c1-102">CorDebugGCType 열거형</span><span class="sxs-lookup"><span data-stu-id="d34c1-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="d34c1-103">가비지 수집기가 실행되고 있는 위치(워크스테이션 또는 서버)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d34c1-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d34c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="d34c1-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d34c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d34c1-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="d34c1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d34c1-106">Members</span></span>  
  
|<span data-ttu-id="d34c1-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="d34c1-107">Member name</span></span>|<span data-ttu-id="d34c1-108">설명</span><span class="sxs-lookup"><span data-stu-id="d34c1-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="d34c1-109">가비지 수집기는 워크스테이션에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34c1-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="d34c1-110">가비지 수집기는 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34c1-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d34c1-111">설명</span><span class="sxs-lookup"><span data-stu-id="d34c1-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d34c1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d34c1-112">Requirements</span></span>  
 <span data-ttu-id="d34c1-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d34c1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d34c1-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d34c1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d34c1-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d34c1-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d34c1-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d34c1-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d34c1-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="d34c1-117">See also</span></span>

- [<span data-ttu-id="d34c1-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="d34c1-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
