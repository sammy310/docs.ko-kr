---
title: ICorDebugObjectValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: e104f8c522af2ee4cd42332b7459f4a2fd185511
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792682"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="f3da2-102">ICorDebugObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3da2-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="f3da2-103">개체를 포함 하는 값을 나타내는 "ICorDebugValue"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3da2-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f3da2-104">Methods</span></span>  
  
|<span data-ttu-id="f3da2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f3da2-105">Method</span></span>|<span data-ttu-id="f3da2-106">설명</span><span class="sxs-lookup"><span data-stu-id="f3da2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3da2-107">GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="f3da2-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="f3da2-108">이 `ICorDebugObjectValue` 참조 하는 개체의 CLR (공용 언어 런타임) <xref:System.Type>에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="f3da2-109">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="f3da2-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="f3da2-110">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-110">Not implemented.</span></span>|  
|[<span data-ttu-id="f3da2-111">GetFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="f3da2-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="f3da2-112">지정 된 클래스의 지정 된 필드 값을 나타내는 [ICorDebugValue](icordebugvalue-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="f3da2-113">GetManagedCopy 메서드</span><span class="sxs-lookup"><span data-stu-id="f3da2-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="f3da2-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-114">Obsolete.</span></span> <span data-ttu-id="f3da2-115">이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="f3da2-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="f3da2-116">GetVirtualMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="f3da2-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="f3da2-117">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-117">Not implemented.</span></span>|  
|[<span data-ttu-id="f3da2-118">IsValueClass 메서드</span><span class="sxs-lookup"><span data-stu-id="f3da2-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="f3da2-119">이 `ICorDebugObjectValue` 참조 하는 개체가 값 형식 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="f3da2-120">SetFromManagedCopy 메서드</span><span class="sxs-lookup"><span data-stu-id="f3da2-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="f3da2-121">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-121">Obsolete.</span></span> <span data-ttu-id="f3da2-122">이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="f3da2-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3da2-123">주의</span><span class="sxs-lookup"><span data-stu-id="f3da2-123">Remarks</span></span>  
 <span data-ttu-id="f3da2-124">`ICorDebugObjectValue`는 디버깅 중인 프로세스가 계속 될 때까지 계속 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3da2-125">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3da2-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3da2-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3da2-126">Requirements</span></span>  
 <span data-ttu-id="f3da2-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3da2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3da2-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3da2-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3da2-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3da2-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3da2-130">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3da2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3da2-131">참조</span><span class="sxs-lookup"><span data-stu-id="f3da2-131">See also</span></span>

- [<span data-ttu-id="f3da2-132">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3da2-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
