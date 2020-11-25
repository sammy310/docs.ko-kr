---
title: ICorDebugFunction 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
ms.openlocfilehash: 668b27932ea7a2bdc244e1ac0bb8e6891cbd4d17
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726300"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="59cc8-102">ICorDebugFunction 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59cc8-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="59cc8-103">관리되는 함수 또는 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="59cc8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-104">Methods</span></span>  
  
|<span data-ttu-id="59cc8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-105">Method</span></span>|<span data-ttu-id="59cc8-106">설명</span><span class="sxs-lookup"><span data-stu-id="59cc8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="59cc8-107">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-107">CreateBreakpoint Method</span></span>](icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="59cc8-108">이 함수의 시작 부분에 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="59cc8-109">GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-109">GetClass Method</span></span>](icordebugfunction-getclass-method.md)|<span data-ttu-id="59cc8-110">이 함수가 멤버인 클래스를 나타내는 ICorDebugClass 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="59cc8-111">GetCurrentVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-111">GetCurrentVersionNumber Method</span></span>](icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="59cc8-112">이 함수에 대 한 최신 편집의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="59cc8-113">GetILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-113">GetILCode Method</span></span>](icordebugfunction-getilcode-method.md)|<span data-ttu-id="59cc8-114">이 함수의 MSIL (Microsoft 중간 언어) 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="59cc8-115">GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-115">GetLocalVarSigToken Method</span></span>](icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="59cc8-116">이 인스턴스가 나타내는 함수의 지역 변수 서명에 대 한 메타 데이터 토큰을 가져옵니다 `ICorDebugFunction` .</span><span class="sxs-lookup"><span data-stu-id="59cc8-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="59cc8-117">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-117">GetModule Method</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="59cc8-118">이 함수가 정의 된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="59cc8-119">GetNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-119">GetNativeCode Method</span></span>](icordebugfunction-getnativecode-method.md)|<span data-ttu-id="59cc8-120">이 함수에 대 한 네이티브 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="59cc8-121">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="59cc8-121">GetToken Method</span></span>](icordebugfunction-gettoken-method.md)|<span data-ttu-id="59cc8-122">이 함수에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59cc8-123">설명</span><span class="sxs-lookup"><span data-stu-id="59cc8-123">Remarks</span></span>  

 <span data-ttu-id="59cc8-124">`ICorDebugFunction`인터페이스가 제네릭 형식 매개 변수가 있는 함수를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="59cc8-125">예를 `ICorDebugFunction` 들어 인스턴스는를 나타내지만는 `Func<T>` 그렇지 않습니다 `Func<string>` .</span><span class="sxs-lookup"><span data-stu-id="59cc8-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="59cc8-126">[ICorDebugILFrame2:: Enumerat 매개 변수](icordebugilframe2-enumeratetypeparameters-method.md) 를 호출 하 여 제네릭 형식 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="59cc8-127">메서드의 메타 데이터 토큰, `mdMethodDef` 및 메서드의 개체 간 관계는 `ICorDebugFunction` 함수에서 편집 하며 계속 하기가 허용 되는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="59cc8-128">함수에서 편집 하며 계속 하기를 사용할 수 없는 경우에는 개체와 토큰 사이에 일 대 일 관계가 있습니다 `ICorDebugFunction` `mdMethodDef` .</span><span class="sxs-lookup"><span data-stu-id="59cc8-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="59cc8-129">즉, 함수에는 하나의 `ICorDebugFunction` 개체와 하나의 `mdMethodDef` 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="59cc8-130">함수에서 편집 하며 계속 하기를 사용할 수 있는 경우에는 개체와 토큰 간에 다대일 관계가 있습니다 `ICorDebugFunction` `mdMethodDef` .</span><span class="sxs-lookup"><span data-stu-id="59cc8-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="59cc8-131">즉, 함수에는 함수 버전 마다 하나씩의 여러 인스턴스가 포함 될 수 `ICorDebugFunction` 있지만 토큰은 하나 뿐입니다 `mdMethodDef` .</span><span class="sxs-lookup"><span data-stu-id="59cc8-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59cc8-132">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59cc8-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59cc8-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59cc8-133">Requirements</span></span>  

 <span data-ttu-id="59cc8-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59cc8-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59cc8-135">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59cc8-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59cc8-136">**라이브러리:**  CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="59cc8-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="59cc8-137">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59cc8-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59cc8-138">참조</span><span class="sxs-lookup"><span data-stu-id="59cc8-138">See also</span></span>

- [<span data-ttu-id="59cc8-139">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59cc8-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
