---
title: ICorDebugProcess5::GetGCHeapInformation 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81c590dd1f3f6682179645fb384cdd82d1d7ed96
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503257"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="936e4-102">ICorDebugProcess5::GetGCHeapInformation 메서드</span><span class="sxs-lookup"><span data-stu-id="936e4-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="936e4-103">현재 열거 가능 여부를 포함 하 여 가비지 컬렉션 힙에 대 한 일반 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="936e4-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="936e4-104">구문</span><span class="sxs-lookup"><span data-stu-id="936e4-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="936e4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="936e4-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="936e4-106">[out] 에 대 한 포인터를 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 가비지 컬렉션 힙에 대 한 일반 정보를 제공 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="936e4-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="936e4-107">설명</span><span class="sxs-lookup"><span data-stu-id="936e4-107">Remarks</span></span>  
 <span data-ttu-id="936e4-108">`ICorDebugProcess5::GetGCHeapInformation` 힙을 열거 하기 전에 메서드를 호출 해야 또는 개별 힙 지역 가비지 수집 프로세스의 구조는 현재 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="936e4-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="936e4-109">가비지 컬렉션 힙에 컬렉션이 진행 중인 동안 진행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="936e4-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="936e4-110">이 고, 그렇지 열거형 유효 하지 않은 가비지 수집 구조를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="936e4-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="936e4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="936e4-111">Requirements</span></span>  
 <span data-ttu-id="936e4-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="936e4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="936e4-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="936e4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="936e4-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="936e4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="936e4-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="936e4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936e4-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="936e4-116">See also</span></span>
- [<span data-ttu-id="936e4-117">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="936e4-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="936e4-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="936e4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
