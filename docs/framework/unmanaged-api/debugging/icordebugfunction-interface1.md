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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca21911f3d16b79887b9d6d8185f8fab17651321
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672993"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="144c7-102">ICorDebugFunction 인터페이스</span><span class="sxs-lookup"><span data-stu-id="144c7-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="144c7-103">관리되는 함수 또는 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="144c7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-104">Methods</span></span>  
  
|<span data-ttu-id="144c7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-105">Method</span></span>|<span data-ttu-id="144c7-106">설명</span><span class="sxs-lookup"><span data-stu-id="144c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="144c7-107">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="144c7-108">이 함수의 시작 부분에 중단점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="144c7-109">GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="144c7-110">이 함수는 멤버의 클래스를 나타내는 ICorDebugClass 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="144c7-111">GetCurrentVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="144c7-112">이 함수에 대 한 최신 편집의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="144c7-113">GetILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="144c7-114">이 함수에 대 한 Microsoft의 MSIL (intermediate language) 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="144c7-115">GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="144c7-116">이 표시 되는 함수의 로컬 변수 서명에 대 한 메타 데이터 토큰을 가져옵니다 `ICorDebugFunction` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="144c7-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="144c7-117">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="144c7-118">이 함수는 정의 된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="144c7-119">GetNativeCode 메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="144c7-120">이 함수에 대 한 네이티브 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="144c7-121">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="144c7-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="144c7-122">이 함수에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="144c7-123">설명</span><span class="sxs-lookup"><span data-stu-id="144c7-123">Remarks</span></span>  
 <span data-ttu-id="144c7-124">`ICorDebugFunction` 인터페이스는 제네릭 형식 매개 변수를 사용 하 여 함수를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="144c7-125">예를 들어를 `ICorDebugFunction` 인스턴스는 나타냅니다 `Func<T>` 있지만 `Func<string>`합니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="144c7-126">호출 [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) 제네릭 형식 매개 변수를 가져오려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="144c7-127">메서드의 메타 데이터 토큰 간의 관계 `mdMethodDef`, 및 메서드의 `ICorDebugFunction` 개체가 함수에서 편집 하며 계속 하기는 허용 하는 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="144c7-128">사이 한 일 관계가 있습니다 편집 하며 계속 하기 함수에 대해 허용 되지 않는 경우는 `ICorDebugFunction` 개체 및 `mdMethodDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="144c7-129">즉, 함수에 하나 `ICorDebugFunction` 개체와 `mdMethodDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="144c7-130">사이 다 대 일 관계가 편집 하며 계속 하기는 함수에 대해 허용 되 면 합니다 `ICorDebugFunction` 개체 및 `mdMethodDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="144c7-131">즉, 함수가 대부분의 있을 `ICorDebugFunction`, 함수의 각 버전에 대 한 있지만 하나만 `mdMethodDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="144c7-132">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="144c7-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="144c7-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="144c7-133">Requirements</span></span>  
 <span data-ttu-id="144c7-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="144c7-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="144c7-135">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="144c7-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="144c7-136">**라이브러리:**  CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="144c7-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="144c7-137">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="144c7-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="144c7-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="144c7-138">See also</span></span>

- [<span data-ttu-id="144c7-139">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="144c7-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
