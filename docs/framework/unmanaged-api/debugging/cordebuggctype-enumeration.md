---
description: '자세히 알아보기: CorDebugGCType 열거형'
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
ms.openlocfilehash: 4be835a9a028a882fa050991beb31d2a8dec5354
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801659"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="b7102-103">CorDebugGCType 열거형</span><span class="sxs-lookup"><span data-stu-id="b7102-103">CorDebugGCType Enumeration</span></span>

<span data-ttu-id="b7102-104">가비지 수집기가 실행되고 있는 위치(워크스테이션 또는 서버)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7102-104">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7102-105">구문</span><span class="sxs-lookup"><span data-stu-id="b7102-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7102-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7102-106">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="b7102-107">구성원</span><span class="sxs-lookup"><span data-stu-id="b7102-107">Members</span></span>  
  
|<span data-ttu-id="b7102-108">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="b7102-108">Member name</span></span>|<span data-ttu-id="b7102-109">설명</span><span class="sxs-lookup"><span data-stu-id="b7102-109">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="b7102-110">워크스테이션에서 가비지 수집기가 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7102-110">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="b7102-111">서버에서 가비지 수집기가 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7102-111">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7102-112">설명</span><span class="sxs-lookup"><span data-stu-id="b7102-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7102-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7102-113">Requirements</span></span>  

 <span data-ttu-id="b7102-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7102-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7102-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7102-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7102-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7102-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7102-117">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7102-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7102-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7102-118">See also</span></span>

- [<span data-ttu-id="b7102-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="b7102-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
