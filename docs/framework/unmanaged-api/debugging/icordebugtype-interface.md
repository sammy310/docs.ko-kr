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
ms.openlocfilehash: 5e88652ff75223e30e6abc454f1e1af91494c7b2
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396699"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="d0d52-102">ICorDebugType 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0d52-102">ICorDebugType Interface</span></span>
<span data-ttu-id="d0d52-103">기본 또는 복합 형식 (즉, 사용자 정의)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0d52-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="d0d52-104">형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0d52-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0d52-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d0d52-105">Methods</span></span>  
  
|<span data-ttu-id="d0d52-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d0d52-106">Method</span></span>|<span data-ttu-id="d0d52-107">Description</span><span class="sxs-lookup"><span data-stu-id="d0d52-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0d52-108">EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="d0d52-108">EnumerateTypeParameters Method</span></span>](icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="d0d52-109"><xref:System.Type>이에서 참조 하는 클래스의 제네릭 매개 변수를 참조 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="d0d52-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="d0d52-110">GetBase 메서드</span><span class="sxs-lookup"><span data-stu-id="d0d52-110">GetBase Method</span></span>](icordebugtype-getbase-method.md)|<span data-ttu-id="d0d52-111">`ICorDebugType`이가 참조 하는 클래스의 기본 클래스 (있는 경우)를 참조 하는에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="d0d52-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="d0d52-112">GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="d0d52-112">GetClass Method</span></span>](icordebugtype-getclass-method.md)|<span data-ttu-id="d0d52-113">이의 형식화 된 생성자를 참조 하는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="d0d52-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="d0d52-114">GetFirstTypeParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="d0d52-114">GetFirstTypeParameter Method</span></span>](icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="d0d52-115">`ICorDebugType` <xref:System.Type> 이에서 참조 하는 클래스의 생성자에 대 한 첫 번째 제네릭 매개 변수를 참조 하는에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="d0d52-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="d0d52-116">GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="d0d52-116">GetRank Method</span></span>](icordebugtype-getrank-method.md)|<span data-ttu-id="d0d52-117">배열 형식의 차원 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d52-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="d0d52-118">GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="d0d52-118">GetStaticFieldValue Method</span></span>](icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="d0d52-119">지정 된 스택 프레임에서 지정 된 필드 토큰이 참조 하는 정적 필드의 값을 포함 하는 ICorDebugValue에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d52-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="d0d52-120">GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="d0d52-120">GetType Method</span></span>](icordebugtype-gettype-method.md)|<span data-ttu-id="d0d52-121">이에서 참조 하는 공용 언어 런타임의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="d0d52-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0d52-122">설명</span><span class="sxs-lookup"><span data-stu-id="d0d52-122">Remarks</span></span>  
 <span data-ttu-id="d0d52-123">형식이 제네릭인 경우는 인스턴스화되지 않은 `ICorDebugClass` 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0d52-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="d0d52-124">`ICorDebugType`인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0d52-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="d0d52-125">예를 들어 해시 테이블 \< K, V>는에 의해 표현 되는 `ICorDebugClass` 반면 해시 테이블 \< Int32, 문자열>는로 `ICorDebugType` 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d52-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="d0d52-126">제네릭이 아닌 형식은 및로 표시 됩니다 `ICorDebugClass` `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="d0d52-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="d0d52-127">후자 인터페이스는 형식 인스턴스화를 처리 하기 위해 .NET Framework 버전 2.0에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d52-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0d52-128">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d52-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0d52-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0d52-129">Requirements</span></span>  
 <span data-ttu-id="d0d52-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0d52-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0d52-131">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0d52-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0d52-132">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0d52-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0d52-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0d52-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d52-134">참조</span><span class="sxs-lookup"><span data-stu-id="d0d52-134">See also</span></span>

- [<span data-ttu-id="d0d52-135">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0d52-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
