---
title: ICorDebugType 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74863af1096f8600b8095e593c1f3c820c512e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166805"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="0d69a-102">ICorDebugType 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d69a-102">ICorDebugType Interface</span></span>
<span data-ttu-id="0d69a-103">형식을, 기본 또는 복합 (즉, 사용자 정의)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="0d69a-104">형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d69a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0d69a-105">Methods</span></span>  
  
|<span data-ttu-id="0d69a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0d69a-106">Method</span></span>|<span data-ttu-id="0d69a-107">설명</span><span class="sxs-lookup"><span data-stu-id="0d69a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d69a-108">EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="0d69a-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="0d69a-109">제네릭 참조 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다 <xref:System.Type> 이 참조 하는 클래스의 매개 변수 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="0d69a-110">GetBase 메서드</span><span class="sxs-lookup"><span data-stu-id="0d69a-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="0d69a-111">한 인터페이스 포인터를 가져옵니다는 `ICorDebugType` 이 참조 하는 클래스의 기본 클래스를 참조 하는 `ICorDebugType`있는 경우.</span><span class="sxs-lookup"><span data-stu-id="0d69a-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="0d69a-112">GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="0d69a-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="0d69a-113">이 형식의 생성자를 참조 하는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="0d69a-114">GetFirstTypeParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="0d69a-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="0d69a-115">한 인터페이스 포인터를 가져옵니다는 `ICorDebugType` 를 참조 하는 첫 번째 제네릭 <xref:System.Type> 이 참조 하는 클래스의 생성자에 대 한 매개 변수 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="0d69a-116">GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="0d69a-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="0d69a-117">배열 형식의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="0d69a-118">GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="0d69a-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="0d69a-119">지정한 스택 프레임에서 토큰에 지정 된 필드에서 참조 하는 정적 필드의 값이 포함 된 ICorDebugValue 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="0d69a-120">GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="0d69a-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="0d69a-121">공용 언어 런타임의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> 이 참조 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d69a-122">설명</span><span class="sxs-lookup"><span data-stu-id="0d69a-122">Remarks</span></span>  
 <span data-ttu-id="0d69a-123">형식이 제네릭인 경우 `ICorDebugClass` 인스턴스화되지 않은 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="0d69a-124">`ICorDebugType` 인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="0d69a-125">예를 들어 Hashtable\<K, V >을 표시 `ICorDebugClass`반면 Hashtable\<Int32, String >을 표시 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="0d69a-126">제네릭이 아닌 형식은 둘 다 표시 됩니다 `ICorDebugClass` 고 `ICorDebugType`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="0d69a-127">두 번째 인터페이스 형식 인스턴스화를 사용 하 여 처리 하는.NET Framework 버전 2.0에서에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d69a-128">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d69a-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d69a-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d69a-129">Requirements</span></span>  
 <span data-ttu-id="0d69a-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d69a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d69a-131">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d69a-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d69a-132">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d69a-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d69a-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d69a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d69a-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="0d69a-134">See also</span></span>

- [<span data-ttu-id="0d69a-135">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d69a-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
