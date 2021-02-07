---
description: '자세히 알아보기: ICorDebugClass 인터페이스'
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
ms.openlocfilehash: 5ded26a8b3a98bd273bbfe1bfa9efd1bb70d5595
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711507"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="05915-103">ICorDebugClass 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05915-103">ICorDebugClass Interface</span></span>

<span data-ttu-id="05915-104">기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05915-104">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="05915-105">형식이 제네릭이면 `ICorDebugClass`는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05915-105">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05915-106">메서드</span><span class="sxs-lookup"><span data-stu-id="05915-106">Methods</span></span>  
  
|<span data-ttu-id="05915-107">메서드</span><span class="sxs-lookup"><span data-stu-id="05915-107">Method</span></span>|<span data-ttu-id="05915-108">설명</span><span class="sxs-lookup"><span data-stu-id="05915-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05915-109">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="05915-109">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="05915-110">이 클래스를 정의 하는 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05915-110">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="05915-111">GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="05915-111">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="05915-112">지정 된 정적 필드의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05915-112">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="05915-113">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="05915-113">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="05915-114">`TypeDef`이 클래스에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05915-114">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05915-115">설명</span><span class="sxs-lookup"><span data-stu-id="05915-115">Remarks</span></span>  

 <span data-ttu-id="05915-116">`ICorDebugClass`인터페이스는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05915-116">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="05915-117">ICorDebugType 인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05915-117">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="05915-118">예를 들어는로 표현 되는 반면는로 표현 됩니다 `Hashtable<K, V>` `ICorDebugClass` `Hashtable<Int32, String>` `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="05915-118">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="05915-119">제네릭이 아닌 형식은 및로 표시 됩니다 `ICorDebugClass` `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="05915-119">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="05915-120">후자 인터페이스는 형식 인스턴스화를 처리 하기 위해 .NET Framework 버전 2.0에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05915-120">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05915-121">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05915-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05915-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05915-122">Requirements</span></span>  

 <span data-ttu-id="05915-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05915-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05915-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05915-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05915-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05915-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05915-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05915-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05915-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05915-127">See also</span></span>

- [<span data-ttu-id="05915-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05915-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
