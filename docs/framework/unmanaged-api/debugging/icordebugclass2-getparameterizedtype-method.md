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
ms.openlocfilehash: 139181975d16c2cdacec10ed646cfc2b8fb31a20
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717996"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="f699d-102">ICorDebugClass2::GetParameterizedType 메서드</span><span class="sxs-lookup"><span data-stu-id="f699d-102">ICorDebugClass2::GetParameterizedType Method</span></span>

<span data-ttu-id="f699d-103">이 클래스에 대 한 형식 선언을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f699d-104">구문</span><span class="sxs-lookup"><span data-stu-id="f699d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f699d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f699d-105">Parameters</span></span>  

 `elementType`  
 <span data-ttu-id="f699d-106">진행 이 클래스의 요소 형식을 지정 하는 CorElementType 열거형의 값입니다 .이 ICorDebugClass2이 값 형식을 나타내는 경우이 값을 ELEMENT_TYPE_VALUETYPE 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="f699d-107">이이 복합 형식을 나타내는 경우이 값을 ELEMENT_TYPE_CLASS 설정 `ICorDebugClass2` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="f699d-108">진행 형식이 제네릭인 경우 형식 매개 변수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="f699d-109">형식 매개 변수 (있는 경우)의 수는 클래스에 필요한 수와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="f699d-110">진행 각각 형식 매개 변수를 나타내는 ICorDebugType 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="f699d-111">제네릭이 아닌 클래스의 경우이 값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="f699d-112">제한이 형식 선언을 나타내는 개체의 주소에 대 한 포인터입니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="f699d-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="f699d-113">이 개체는 <xref:System.Type> 관리 코드의 개체와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f699d-114">설명</span><span class="sxs-lookup"><span data-stu-id="f699d-114">Remarks</span></span>  

 <span data-ttu-id="f699d-115">클래스가 제네릭이 아닌 경우 즉, 형식 매개 변수가 없는 경우에는 `GetParameterizedType` 클래스에 해당 하는 런타임 형식 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="f699d-116">이 `elementType` 매개 변수는 클래스에 대 한 올바른 요소 형식으로 설정 해야 합니다. 클래스가 값 형식이 면 ELEMENT_TYPE_VALUETYPE이 고, 그렇지 않으면 ELEMENT_TYPE_CLASS입니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="f699d-117">클래스에서 형식 매개 변수를 허용 하는 경우 (예 `ArrayList<T>` :)를 사용 `GetParameterizedType` 하 여와 같은 인스턴스화된 형식에 대 한 형식 개체를 생성할 수 있습니다 `ArrayList<int>` .</span><span class="sxs-lookup"><span data-stu-id="f699d-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="f699d-118">배경 정보</span><span class="sxs-lookup"><span data-stu-id="f699d-118">Background Information</span></span>  

 <span data-ttu-id="f699d-119">.NET Framework 버전 1.0 및 1.1에서 메타 데이터의 모든 형식은 실행 중인 프로세스의 형식에 직접 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="f699d-120">따라서 메타 데이터 형식과 런타임 형식은 실행 중인 프로세스에서 단일 표현을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="f699d-121">그러나 메타 데이터의 한 제네릭 형식은 실행 중인 프로세스에서 형식의 여러 인스턴스에 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="f699d-122">예를 들어 메타 데이터 형식은 `SortedList<K,V>` ,, 등으로 매핑될 수 있습니다 `SortedList<String, EmployeeRecord>` `SortedList<Int32, String>` `SortedList<String,Array<Int32>>` .</span><span class="sxs-lookup"><span data-stu-id="f699d-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="f699d-123">따라서 형식 인스턴스화를 처리 하는 방법이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="f699d-124">.NET Framework 버전 2.0는 인터페이스를 소개 합니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="f699d-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="f699d-125">제네릭 형식의 경우 `ICorDebugClass` 또는 `ICorDebugClass2` 개체는 인스턴스화되지 않은 형식 ( `SortedList<K,V>` )을 나타내며 개체는 `ICorDebugType` 다양 한 인스턴스화된 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="f699d-126">또는 개체가 지정 된 경우 `ICorDebugClass` `ICorDebugClass2` `ICorDebugType` 메서드를 호출 하 여 모든 인스턴스화에 대 한 개체를 만들 수 있습니다 `ICorDebugClass2::GetParameterizedType` .</span><span class="sxs-lookup"><span data-stu-id="f699d-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="f699d-127">또한 `ICorDebugType` Int32와 같은 단순 형식 또는 제네릭이 아닌 형식에 대 한 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="f699d-128">형식에 대 한 `ICorDebugType` 런타임 개념을 나타내는 개체를 도입 하면 API 전체에 걸쳐 ripple 효과가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f699d-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="f699d-129">이전에 `ICorDebugClass` 또는 `ICorDebugClass2` 개체나 값을 사용 하 던 함수는 `CorElementType` 개체를 사용 하기 위해 일반화 됩니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="f699d-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f699d-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f699d-130">Requirements</span></span>  

 <span data-ttu-id="f699d-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f699d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f699d-132">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f699d-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f699d-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f699d-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f699d-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f699d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
