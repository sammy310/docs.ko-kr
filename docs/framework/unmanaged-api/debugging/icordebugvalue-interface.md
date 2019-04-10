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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdc889dd6b2854654bfe43b24afbe4cc19863c80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227823"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="2781e-102">ICorDebugValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2781e-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="2781e-103">디버깅 중인 프로세스에서 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="2781e-104">읽기 또는 쓰기 값 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2781e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2781e-105">Methods</span></span>  
  
|<span data-ttu-id="2781e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2781e-106">Method</span></span>|<span data-ttu-id="2781e-107">설명</span><span class="sxs-lookup"><span data-stu-id="2781e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2781e-108">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="2781e-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="2781e-109">이 메서드가 현재 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="2781e-110">GetAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="2781e-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="2781e-111">이 주소를 가져옵니다 `ICorDebugValue` 디버깅 중인 프로세스에 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="2781e-112">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2781e-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="2781e-113">이 바이트 단위로 크기를 가져옵니다 `ICorDebugValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="2781e-114">GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="2781e-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="2781e-115">이 기본 형식을 가져옵니다 `ICorDebugValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2781e-116">설명</span><span class="sxs-lookup"><span data-stu-id="2781e-116">Remarks</span></span>  
 <span data-ttu-id="2781e-117">일반적으로 반환 될 때 값 개체의 소유권 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="2781e-118">수신자는 개체를 사용 하 여 완료 되 면 개체에서 참조를 제거 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="2781e-119">값에서 검색 된 위치에 따라 값 남아 있을 수 없습니다 유효한 프로세스 다시 시작 된 후입니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="2781e-120">따라서 일반적으로 해서는 안 됩니다 수 있는 값의 호출을 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="2781e-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2781e-121">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2781e-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2781e-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2781e-122">Requirements</span></span>  
 <span data-ttu-id="2781e-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2781e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2781e-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2781e-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2781e-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2781e-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2781e-126">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="2781e-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2781e-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="2781e-127">See also</span></span>

- [<span data-ttu-id="2781e-128">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2781e-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="2781e-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2781e-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
