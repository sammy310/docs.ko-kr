---
title: ICorDebugGenericValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad2209c6e28c7749bd149902e5b696955ee7f13f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988678"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="59b3d-102">ICorDebugGenericValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59b3d-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="59b3d-103">모든 값에 적용 되는 "ICorDebugValue"의 하위 클래스.</span><span class="sxs-lookup"><span data-stu-id="59b3d-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="59b3d-104">이 인터페이스에서는 값의 Get 및 Set 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59b3d-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="59b3d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="59b3d-105">Methods</span></span>  
  
|<span data-ttu-id="59b3d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="59b3d-106">Method</span></span>|<span data-ttu-id="59b3d-107">설명</span><span class="sxs-lookup"><span data-stu-id="59b3d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="59b3d-108">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="59b3d-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="59b3d-109">지정된 된 버퍼에 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="59b3d-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="59b3d-110">SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="59b3d-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="59b3d-111">지정된 된 버퍼에서 새 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="59b3d-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59b3d-112">설명</span><span class="sxs-lookup"><span data-stu-id="59b3d-112">Remarks</span></span>  
 <span data-ttu-id="59b3d-113">`ICorDebugGenericValue` 비-원격 이기 때문에 하위 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="59b3d-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="59b3d-114">참조 형식에 대해 값이 참조의 콘텐츠 대신 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b3d-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="59b3d-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59b3d-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59b3d-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59b3d-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b3d-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59b3d-117">Requirements</span></span>  
 <span data-ttu-id="59b3d-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="59b3d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59b3d-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59b3d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59b3d-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59b3d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59b3d-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59b3d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b3d-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="59b3d-122">See also</span></span>

- [<span data-ttu-id="59b3d-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59b3d-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
