---
title: ICorDebugEval::CreateValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
ms.openlocfilehash: 4bb04ba090be9cab551bc39d8d9f1be974c747d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085130"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="13e99-102">ICorDebugEval::CreateValue 메서드</span><span class="sxs-lookup"><span data-stu-id="13e99-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="13e99-103">초기 값이 0 또는 null 인 지정 된 형식의 값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="13e99-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="13e99-105">대신 [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) 을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="13e99-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13e99-106">구문</span><span class="sxs-lookup"><span data-stu-id="13e99-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13e99-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13e99-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="13e99-108">진행 값의 형식을 지정 하는 [Corelementtype](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="13e99-109">진행 형식이 기본 형식이 아닌 경우 값의 클래스를 지정 하는 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="13e99-110">제한이 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13e99-111">주의</span><span class="sxs-lookup"><span data-stu-id="13e99-111">Remarks</span></span>  
 <span data-ttu-id="13e99-112">`CreateValue`는 함수 실행에서 사용 하는 용도로만 지정 된 형식의 `ICorDebugValue` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="13e99-113">이 값 개체를 사용 하 여 사용자 상수를 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="13e99-114">값의 형식이 기본 형식이 면 해당 초기 값은 0 또는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="13e99-115">[ICorDebugGenericValue:: SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) 를 사용 하 여 기본 형식 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="13e99-116">`elementType` 값이 ELEMENT_TYPE_CLASS 인 경우 null 개체 참조를 나타내는 "ICorDebugReferenceValue" (`ppValue`로 반환 됨)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="13e99-117">이 개체를 사용 하 여 개체 참조 매개 변수가 있는 함수 실행에 null을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="13e99-118">`ICorDebugValue`를 어떤 것도 설정할 수 없습니다. 항상 null로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13e99-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13e99-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13e99-119">Requirements</span></span>  
 <span data-ttu-id="13e99-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13e99-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13e99-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13e99-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13e99-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13e99-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13e99-123">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="13e99-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e99-124">참조</span><span class="sxs-lookup"><span data-stu-id="13e99-124">See also</span></span>

- [<span data-ttu-id="13e99-125">CreateValueForType 메서드</span><span class="sxs-lookup"><span data-stu-id="13e99-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="13e99-126">ICorDebugEval 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13e99-126">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
