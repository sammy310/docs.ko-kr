---
title: ICorDebugObjectValue::GetClass 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: b0e8fd162ccc1cfc944fb870f493febfe2e5ef42
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207676"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="b9715-102">ICorDebugObjectValue::GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="b9715-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="b9715-103">이 개체 값의 클래스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b9715-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9715-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9715-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9715-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9715-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="b9715-106">제한이 이 "ICorDebugObjectValue" 개체로 표시 되는 개체 값의 클래스를 나타내는 "ICorDebugClass" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b9715-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9715-107">설명</span><span class="sxs-lookup"><span data-stu-id="b9715-107">Remarks</span></span>  
 <span data-ttu-id="b9715-108">`GetClass`및 [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) 메서드는 각각 값의 형식에 대 한 정보를 반환 하며, 둘 다 제네릭 인식 [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md)로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9715-108">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9715-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9715-109">Requirements</span></span>  
 <span data-ttu-id="b9715-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9715-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9715-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9715-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9715-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9715-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9715-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9715-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9715-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9715-114">See also</span></span>
