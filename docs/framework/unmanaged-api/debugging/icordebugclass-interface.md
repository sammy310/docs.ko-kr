---
title: ICorDebugClass 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: 4f488741f4233f06c128e0a262ce798ef27af3ff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699640"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="54dc5-102">ICorDebugClass 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54dc5-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="54dc5-103">기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54dc5-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="54dc5-104">형식이 제네릭이면 `ICorDebugClass`는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54dc5-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54dc5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="54dc5-105">Methods</span></span>  
  
|<span data-ttu-id="54dc5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="54dc5-106">Method</span></span>|<span data-ttu-id="54dc5-107">설명</span><span class="sxs-lookup"><span data-stu-id="54dc5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54dc5-108">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="54dc5-108">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="54dc5-109">이 클래스를 정의 하는 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="54dc5-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="54dc5-110">GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="54dc5-110">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="54dc5-111">지정 된 정적 필드의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="54dc5-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="54dc5-112">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="54dc5-112">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="54dc5-113">`TypeDef`이 클래스에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="54dc5-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54dc5-114">설명</span><span class="sxs-lookup"><span data-stu-id="54dc5-114">Remarks</span></span>  

 <span data-ttu-id="54dc5-115">`ICorDebugClass`인터페이스는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54dc5-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="54dc5-116">ICorDebugType 인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="54dc5-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="54dc5-117">예를 들어는로 표현 되는 반면는로 표현 됩니다 `Hashtable<K, V>` `ICorDebugClass` `Hashtable<Int32, String>` `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="54dc5-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="54dc5-118">제네릭이 아닌 형식은 및로 표시 됩니다 `ICorDebugClass` `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="54dc5-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="54dc5-119">후자 인터페이스는 형식 인스턴스화를 처리 하기 위해 .NET Framework 버전 2.0에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="54dc5-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54dc5-120">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54dc5-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54dc5-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54dc5-121">Requirements</span></span>  

 <span data-ttu-id="54dc5-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54dc5-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54dc5-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54dc5-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54dc5-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54dc5-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54dc5-125">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54dc5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54dc5-126">참조</span><span class="sxs-lookup"><span data-stu-id="54dc5-126">See also</span></span>

- [<span data-ttu-id="54dc5-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54dc5-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
