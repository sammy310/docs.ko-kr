---
description: '자세히 알아보기: ICorDebugObjectValue 인터페이스'
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
ms.openlocfilehash: a2af438bbb4c2f56eb1a72151e339b6b0a978eec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794774"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="be28f-103">ICorDebugObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be28f-103">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="be28f-104">개체를 포함 하는 값을 나타내는 "ICorDebugValue"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="be28f-104">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be28f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="be28f-105">Methods</span></span>  
  
|<span data-ttu-id="be28f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="be28f-106">Method</span></span>|<span data-ttu-id="be28f-107">설명</span><span class="sxs-lookup"><span data-stu-id="be28f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be28f-108">GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="be28f-108">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="be28f-109"><xref:System.Type>이가 참조 하는 개체의 CLR (공용 언어 런타임)에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugObjectValue` .</span><span class="sxs-lookup"><span data-stu-id="be28f-109">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="be28f-110">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="be28f-110">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="be28f-111">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="be28f-111">Not implemented.</span></span>|  
|[<span data-ttu-id="be28f-112">GetFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="be28f-112">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="be28f-113">지정 된 클래스의 지정 된 필드 값을 나타내는 [ICorDebugValue](icordebugvalue-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="be28f-113">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="be28f-114">GetManagedCopy 메서드</span><span class="sxs-lookup"><span data-stu-id="be28f-114">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="be28f-115">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be28f-115">Obsolete.</span></span> <span data-ttu-id="be28f-116">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="be28f-116">Do not call this method.</span></span>|  
|[<span data-ttu-id="be28f-117">GetVirtualMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="be28f-117">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="be28f-118">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="be28f-118">Not implemented.</span></span>|  
|[<span data-ttu-id="be28f-119">IsValueClass 메서드</span><span class="sxs-lookup"><span data-stu-id="be28f-119">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="be28f-120">이에서 참조 하는 개체가 값 형식 인지 여부를 나타내는 값을 가져옵니다 `ICorDebugObjectValue` .</span><span class="sxs-lookup"><span data-stu-id="be28f-120">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="be28f-121">SetFromManagedCopy 메서드</span><span class="sxs-lookup"><span data-stu-id="be28f-121">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="be28f-122">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be28f-122">Obsolete.</span></span> <span data-ttu-id="be28f-123">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="be28f-123">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be28f-124">설명</span><span class="sxs-lookup"><span data-stu-id="be28f-124">Remarks</span></span>  

 <span data-ttu-id="be28f-125">는 `ICorDebugObjectValue` 디버그 중인 프로세스가 계속 될 때까지 유효한 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be28f-125">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be28f-126">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be28f-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be28f-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be28f-127">Requirements</span></span>  

 <span data-ttu-id="be28f-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be28f-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be28f-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be28f-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be28f-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be28f-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be28f-131">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be28f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be28f-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be28f-132">See also</span></span>

- [<span data-ttu-id="be28f-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be28f-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
