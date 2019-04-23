---
title: COR_HEAPINFO 구조체
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23bda470b8b5812b567081ba268ad503ac39ecaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090357"
---
# <a name="corheapinfo-structure"></a><span data-ttu-id="61359-102">COR_HEAPINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="61359-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="61359-103">가비지 수집 힙에 대한 일반 정보(열거 가능 여부 포함)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61359-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61359-104">구문</span><span class="sxs-lookup"><span data-stu-id="61359-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="61359-105">멤버</span><span class="sxs-lookup"><span data-stu-id="61359-105">Members</span></span>  
  
|<span data-ttu-id="61359-106">멤버</span><span class="sxs-lookup"><span data-stu-id="61359-106">Member</span></span>|<span data-ttu-id="61359-107">설명</span><span class="sxs-lookup"><span data-stu-id="61359-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="61359-108">`true` 가비지 수집 구조 유효 하 고 힙을 열거할 수 있습니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="61359-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="61359-109">대상 아키텍처에 대 한 포인터의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="61359-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="61359-110">프로세스에 힙 논리 가비지 수집 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="61359-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="61359-111">`TRUE` 동시 경우 (백그라운드) 가비지 컬렉션이 설정 되었는지; 그렇지 않으면 `FALSE`합니다.</span><span class="sxs-lookup"><span data-stu-id="61359-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="61359-112">멤버는 [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) 워크스테이션 또는 서버에서 가비지 수집기가 실행 중인지 여부를 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="61359-112">A member of the [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61359-113">설명</span><span class="sxs-lookup"><span data-stu-id="61359-113">Remarks</span></span>  
 <span data-ttu-id="61359-114">인스턴스를 `COR_HEAPINFO` 구조 호출에서 반환 되는 [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="61359-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="61359-115">가비지 컬렉션 힙에 개체를 열거 하기 전에 항상 체크 합니다 `areGCStructuresValid` 필드 힙을 열거 가능한 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61359-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="61359-116">자세한 내용은 참조는 [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="61359-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61359-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61359-117">Requirements</span></span>  
 <span data-ttu-id="61359-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="61359-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61359-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61359-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61359-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61359-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61359-121">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61359-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61359-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="61359-122">See also</span></span>

- [<span data-ttu-id="61359-123">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="61359-123">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="61359-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="61359-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
