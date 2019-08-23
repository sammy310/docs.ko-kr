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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5099af23a2b706694bfcb655d295607c97ea8a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969274"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="6451d-102">ICorDebugClass 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6451d-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="6451d-103">기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="6451d-104">형식이 제네릭이면 `ICorDebugClass`는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6451d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6451d-105">Methods</span></span>  
  
|<span data-ttu-id="6451d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6451d-106">Method</span></span>|<span data-ttu-id="6451d-107">Description</span><span class="sxs-lookup"><span data-stu-id="6451d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6451d-108">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="6451d-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="6451d-109">이 클래스를 정의 하는 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="6451d-110">GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="6451d-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="6451d-111">지정 된 정적 필드의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="6451d-112">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="6451d-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="6451d-113">이 클래스 `TypeDef` 에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6451d-114">설명</span><span class="sxs-lookup"><span data-stu-id="6451d-114">Remarks</span></span>  
 <span data-ttu-id="6451d-115">인터페이스 `ICorDebugClass` 는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="6451d-116">ICorDebugType 인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="6451d-117">예 `Hashtable<K, V>` `Hashtable<Int32, String>` `ICorDebugType`를 들어는로 표현 되는 반면는로 표현 됩니다. `ICorDebugClass`</span><span class="sxs-lookup"><span data-stu-id="6451d-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="6451d-118">제네릭이 아닌 형식은 `ICorDebugClass` 및 `ICorDebugType`로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="6451d-119">후자 인터페이스는 형식 인스턴스화를 처리 하기 위해 .NET Framework 버전 2.0에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6451d-120">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6451d-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6451d-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6451d-121">Requirements</span></span>  
 <span data-ttu-id="6451d-122">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6451d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6451d-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6451d-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6451d-124">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6451d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6451d-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6451d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6451d-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="6451d-126">See also</span></span>

- [<span data-ttu-id="6451d-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6451d-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
