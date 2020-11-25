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
ms.openlocfilehash: 06f403f0b653866428a41240f99833ec1180eb86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731081"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="5d72f-102">ICorDebugValue::GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="5d72f-102">ICorDebugValue::GetType Method</span></span>

<span data-ttu-id="5d72f-103">이 "ICorDebugValue" 개체의 기본 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d72f-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d72f-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d72f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d72f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d72f-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="5d72f-106">제한이 값의 형식을 나타내는 "CorElementType" 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d72f-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d72f-107">설명</span><span class="sxs-lookup"><span data-stu-id="5d72f-107">Remarks</span></span>  

 <span data-ttu-id="5d72f-108">개체가 복잡 한 런타임 형식이 면 해당 형식은 인터페이스의 적절 한 서브 클래스를 통해 검사할 수 있습니다 `ICorDebugValue` .</span><span class="sxs-lookup"><span data-stu-id="5d72f-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="5d72f-109">예를 들어,에서 상속 되는 "ICorDebugObjectValue" `ICorDebugValue` 은 복합 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d72f-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="5d72f-110">`GetType`및 [ICorDebugObjectValue:: getclass](icordebugobjectvalue-getclass-method.md) 메서드는 각각 값의 형식에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d72f-110">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="5d72f-111">둘 다 제네릭 인식 [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) 메서드로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d72f-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d72f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d72f-112">Requirements</span></span>  

 <span data-ttu-id="5d72f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d72f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d72f-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d72f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d72f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d72f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d72f-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d72f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d72f-117">참조</span><span class="sxs-lookup"><span data-stu-id="5d72f-117">See also</span></span>
