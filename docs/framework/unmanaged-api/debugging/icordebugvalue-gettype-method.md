---
title: ICorDebugValue::GetType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0dbdee35e6c73fbf2d73edd8a6c479e2f2882ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764320"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="e5600-102">ICorDebugValue::GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="e5600-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="e5600-103">이 "ICorDebugValue" 개체의 기본 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e5600-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5600-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5600-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5600-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5600-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="e5600-106">[out] 값의 형식을 나타내는 "CorElementType" 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5600-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5600-107">설명</span><span class="sxs-lookup"><span data-stu-id="e5600-107">Remarks</span></span>  
 <span data-ttu-id="e5600-108">개체는 복잡 한 런타임 형식인 경우 해당 형식을의 적절 한 서브 클래스를 통해 검사할 수 있습니다는 `ICorDebugValue` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e5600-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="e5600-109">예를 들어, "ICorDebugObjectValue"에서 상속 되는 `ICorDebugValue`, 복합 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5600-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="e5600-110">합니다 `GetType` 하 고 [icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) 메서드는 각 값의 형식에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5600-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="e5600-111">모두를 제네릭 인식으로 대체 [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e5600-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5600-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5600-112">Requirements</span></span>  
 <span data-ttu-id="e5600-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5600-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5600-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5600-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5600-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5600-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5600-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5600-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5600-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="e5600-117">See also</span></span>
