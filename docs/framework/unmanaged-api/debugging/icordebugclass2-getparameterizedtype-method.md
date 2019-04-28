---
title: ICorDebugClass2::GetParameterizedType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e1734ca91fd48cc15b8dbf25f11518ed0455b6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750776"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="d76aa-102">ICorDebugClass2::GetParameterizedType 메서드</span><span class="sxs-lookup"><span data-stu-id="d76aa-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="d76aa-103">이 클래스에 대 한 형식 선언을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d76aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="d76aa-104">Syntax</span></span>  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d76aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d76aa-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="d76aa-106">[in] CorElementType 열거형이 클래스에 대 한 요소 유형을 지정 하는 값입니다. 이 ICorDebugClass2 값 형식을 나타내면 ELEMENT_TYPE_VALUETYPE로이 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="d76aa-107">이 경우이 값 ELEMENT_TYPE_CLASS로 `ICorDebugClass2` 복합 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="d76aa-108">[in] 형식이 제네릭인 경우 형식 매개 변수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="d76aa-109">형식 매개 변수 (있는 경우)의 수에는 클래스에 필요한 번호와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="d76aa-110">[in] 형식 매개 변수를 나타내는 ICorDebugType 개체를 가리키는 각각 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="d76aa-111">클래스의 제네릭이 아닌 경우이 값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="d76aa-112">[out] 주소에 대 한 포인터는 `ICorDebugType` 형식 선언을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="d76aa-113">이 개체는 해당 하는 <xref:System.Type> 관리 되는 코드의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d76aa-114">설명</span><span class="sxs-lookup"><span data-stu-id="d76aa-114">Remarks</span></span>  
 <span data-ttu-id="d76aa-115">클래스는 제네릭이 아닌 즉, 형식 매개 변수가 없는 있으면 경우 `GetParameterizedType` 단순히 클래스에 해당 하는 런타임 형식 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="d76aa-116">`elementType` 클래스에 대 한 올바른 요소 형식으로 매개 변수를 설정 해야 합니다. 클래스는 값 형식; 변수 그렇지 않으면 ELEMENT_TYPE_CLASS 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="d76aa-117">클래스 형식 매개 변수를 허용 하는 경우 (예를 들어 `ArrayList<T>`)를 사용할 수 있습니다 `GetParameterizedType` 과 같은 인스턴스화된 형식에 대 한 형식 개체를 생성 하 `ArrayList<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="d76aa-118">배경 정보</span><span class="sxs-lookup"><span data-stu-id="d76aa-118">Background Information</span></span>  
 <span data-ttu-id="d76aa-119">.NET Framework 버전 1.0 및 1.1에서는 메타 데이터의 형식은 모두 실행 중인 프로세스의 형식으로 직접 매핑할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="d76aa-120">따라서 메타 데이터 형식 및 런타임 형식에서 실행 중인 프로세스를 단일 표현을 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="d76aa-121">그러나 메타 데이터에서 제네릭 형식 하나는 많은 여러 인스턴스에서 실행 중인 프로세스의 형식에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="d76aa-122">예를 들어, 메타 데이터 형식 `SortedList<K,V>` 매핑할 수 있습니다 `SortedList<String, EmployeeRecord>`를 `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`등입니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="d76aa-123">따라서 형식 인스턴스화를 처리 하는 방법을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="d76aa-124">.NET Framework 버전 2.0에 도입 된 `ICorDebugType` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="d76aa-125">제네릭 형식에 대 한는 `ICorDebugClass` 하거나 `ICorDebugClass2` 개체가 인스턴스화되지 않은 형식을 나타내는 (`SortedList<K,V>`), 및 `ICorDebugType` 개체는 다양 한 인스턴스화된 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="d76aa-126">지정 된는 `ICorDebugClass` 또는 `ICorDebugClass2` 개체를 만들 수 있습니다는 `ICorDebugType` 호출 하 여 모든 인스턴스화에 대 한 개체는 `ICorDebugClass2::GetParameterizedType` 메서드.</span><span class="sxs-lookup"><span data-stu-id="d76aa-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="d76aa-127">만들 수도 있습니다는 `ICorDebugType` Int32 등의 단순 형식 또는 제네릭이 아닌 형식에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="d76aa-128">도입 된 `ICorDebugType` 형식의 런타임 개념을 나타내는 개체를 API 전반에 걸쳐 파급 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="d76aa-129">이전에 함수는 `ICorDebugClass` 또는 `ICorDebugClass2` 개체 또는 심지어는 `CorElementType` 값이 사용 하도록 일반화 되었습니다는 `ICorDebugType` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d76aa-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d76aa-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d76aa-130">Requirements</span></span>  
 <span data-ttu-id="d76aa-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d76aa-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d76aa-132">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d76aa-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d76aa-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d76aa-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d76aa-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d76aa-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
