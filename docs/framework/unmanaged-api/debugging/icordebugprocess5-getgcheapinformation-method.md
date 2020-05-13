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
ms.openlocfilehash: 62d45da44a95eae399fbbd287aa997a5f913d0b0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209658"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="62509-102">ICorDebugProcess5::GetGCHeapInformation 메서드</span><span class="sxs-lookup"><span data-stu-id="62509-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="62509-103">가비지 수집 힙에 대 한 일반 정보를 제공 합니다 (현재 열거 가능한 지 여부 포함).</span><span class="sxs-lookup"><span data-stu-id="62509-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62509-104">구문</span><span class="sxs-lookup"><span data-stu-id="62509-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62509-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62509-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="62509-106">제한이 가비지 수집 힙에 대 한 일반 정보를 제공 하는 [COR_HEAPINFO](cor-heapinfo-structure.md) 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62509-106">[out] A pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62509-107">설명</span><span class="sxs-lookup"><span data-stu-id="62509-107">Remarks</span></span>  
 <span data-ttu-id="62509-108">`ICorDebugProcess5::GetGCHeapInformation`프로세스의 가비지 수집 구조가 현재 유효한 지 확인 하기 위해 힙 또는 개별 힙 영역을 열거 하기 전에 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62509-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="62509-109">컬렉션이 진행 중인 동안에는 가비지 컬렉션 힙을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62509-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="62509-110">그렇지 않으면 열거에서 잘못 된 가비지 수집 구조를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62509-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62509-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62509-111">Requirements</span></span>  
 <span data-ttu-id="62509-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62509-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62509-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62509-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62509-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62509-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62509-115">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62509-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62509-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62509-116">See also</span></span>

- [<span data-ttu-id="62509-117">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62509-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="62509-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62509-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
