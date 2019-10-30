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
ms.openlocfilehash: b782207503a2c3f739a30f68d509e6b481d2b6a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129761"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="d9dc7-102">ICorDebugObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9dc7-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="d9dc7-103">개체를 포함 하는 값을 나타내는 "ICorDebugValue"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9dc7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d9dc7-104">Methods</span></span>  
  
|<span data-ttu-id="d9dc7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d9dc7-105">Method</span></span>|<span data-ttu-id="d9dc7-106">설명</span><span class="sxs-lookup"><span data-stu-id="d9dc7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9dc7-107">GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="d9dc7-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="d9dc7-108">이 `ICorDebugObjectValue` 참조 하는 개체의 CLR (공용 언어 런타임) <xref:System.Type>에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="d9dc7-109">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="d9dc7-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="d9dc7-110">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-110">Not implemented.</span></span>|  
|[<span data-ttu-id="d9dc7-111">GetFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="d9dc7-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="d9dc7-112">지정 된 클래스의 지정 된 필드 값을 나타내는 [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="d9dc7-113">GetManagedCopy 메서드</span><span class="sxs-lookup"><span data-stu-id="d9dc7-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="d9dc7-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-114">Obsolete.</span></span> <span data-ttu-id="d9dc7-115">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="d9dc7-116">GetVirtualMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="d9dc7-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="d9dc7-117">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-117">Not implemented.</span></span>|  
|[<span data-ttu-id="d9dc7-118">IsValueClass 메서드</span><span class="sxs-lookup"><span data-stu-id="d9dc7-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="d9dc7-119">이 `ICorDebugObjectValue` 참조 하는 개체가 값 형식 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="d9dc7-120">SetFromManagedCopy 메서드</span><span class="sxs-lookup"><span data-stu-id="d9dc7-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="d9dc7-121">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-121">Obsolete.</span></span> <span data-ttu-id="d9dc7-122">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9dc7-123">주의</span><span class="sxs-lookup"><span data-stu-id="d9dc7-123">Remarks</span></span>  
 <span data-ttu-id="d9dc7-124">`ICorDebugObjectValue`는 디버깅 중인 프로세스가 계속 될 때까지 계속 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9dc7-125">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9dc7-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9dc7-126">Requirements</span></span>  
 <span data-ttu-id="d9dc7-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9dc7-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9dc7-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9dc7-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9dc7-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9dc7-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9dc7-130">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9dc7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9dc7-131">참조</span><span class="sxs-lookup"><span data-stu-id="d9dc7-131">See also</span></span>

- [<span data-ttu-id="d9dc7-132">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9dc7-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
