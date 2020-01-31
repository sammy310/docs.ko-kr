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
ms.openlocfilehash: 6f4c96517375df4cd249b72953bf37812a498c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789355"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="03e85-102">CorDebugGCType 열거형</span><span class="sxs-lookup"><span data-stu-id="03e85-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="03e85-103">가비지 수집기가 실행되고 있는 위치(워크스테이션 또는 서버)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03e85-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03e85-104">구문</span><span class="sxs-lookup"><span data-stu-id="03e85-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="03e85-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03e85-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="03e85-106">Members</span><span class="sxs-lookup"><span data-stu-id="03e85-106">Members</span></span>  
  
|<span data-ttu-id="03e85-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="03e85-107">Member name</span></span>|<span data-ttu-id="03e85-108">설명</span><span class="sxs-lookup"><span data-stu-id="03e85-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="03e85-109">워크스테이션에서 가비지 수집기가 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e85-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="03e85-110">서버에서 가비지 수집기가 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e85-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03e85-111">주의</span><span class="sxs-lookup"><span data-stu-id="03e85-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03e85-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03e85-112">Requirements</span></span>  
 <span data-ttu-id="03e85-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e85-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03e85-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03e85-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03e85-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03e85-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03e85-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03e85-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e85-117">참조</span><span class="sxs-lookup"><span data-stu-id="03e85-117">See also</span></span>

- [<span data-ttu-id="03e85-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="03e85-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
