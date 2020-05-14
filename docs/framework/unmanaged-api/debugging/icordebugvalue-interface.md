---
title: ICorDebugValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: b8d2e49031e59db0527de3c848d7d390095797bf
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396787"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="f5823-102">ICorDebugValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5823-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="f5823-103">디버그 중인 프로세스의 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5823-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="f5823-104">값은 읽기 또는 쓰기 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5823-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5823-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f5823-105">Methods</span></span>  
  
|<span data-ttu-id="f5823-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f5823-106">Method</span></span>|<span data-ttu-id="f5823-107">Description</span><span class="sxs-lookup"><span data-stu-id="f5823-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5823-108">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="f5823-108">CreateBreakpoint Method</span></span>](icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="f5823-109">현재 이 메서드는 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5823-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="f5823-110">GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="f5823-110">GetAddress Method</span></span>](icordebugvalue-getaddress-method.md)|<span data-ttu-id="f5823-111">디버깅 중인이 개체의 주소를 가져옵니다 `ICorDebugValue` .</span><span class="sxs-lookup"><span data-stu-id="f5823-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="f5823-112">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="f5823-112">GetSize Method</span></span>](icordebugvalue-getsize-method.md)|<span data-ttu-id="f5823-113">이 개체의 크기 (바이트)를 가져옵니다 `ICorDebugValue` .</span><span class="sxs-lookup"><span data-stu-id="f5823-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="f5823-114">GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="f5823-114">GetType Method</span></span>](icordebugvalue-gettype-method.md)|<span data-ttu-id="f5823-115">이 개체의 기본 형식을 가져옵니다 `ICorDebugValue` .</span><span class="sxs-lookup"><span data-stu-id="f5823-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5823-116">설명</span><span class="sxs-lookup"><span data-stu-id="f5823-116">Remarks</span></span>  
 <span data-ttu-id="f5823-117">일반적으로 값 개체의 소유권은 반환 될 때 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5823-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="f5823-118">개체를 사용 하 여 작업이 완료 되 면 수신자는 개체에서 참조를 제거할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5823-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="f5823-119">값이 검색 된 위치에 따라 프로세스가 다시 시작 된 후에는 값이 유효 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5823-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="f5823-120">따라서 일반적으로 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 메서드를 호출 하는 동안 값을 보유 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5823-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5823-121">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5823-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5823-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5823-122">Requirements</span></span>  
 <span data-ttu-id="f5823-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5823-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5823-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5823-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5823-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5823-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5823-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5823-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5823-127">참조</span><span class="sxs-lookup"><span data-stu-id="f5823-127">See also</span></span>

- [<span data-ttu-id="f5823-128">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5823-128">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="f5823-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5823-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
