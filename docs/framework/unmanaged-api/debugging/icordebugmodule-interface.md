---
title: ICorDebugModule 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
ms.openlocfilehash: 86e17b48bc491c45f8b46be23ab626dc1f2a6962
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709845"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="327e6-102">ICorDebugModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="327e6-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="327e6-103">실행 파일 또는 DLL (동적 연결 라이브러리) 인 CLR (공용 언어 런타임) 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="327e6-104">메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-104">Methods</span></span>  
  
|<span data-ttu-id="327e6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-105">Method</span></span>|<span data-ttu-id="327e6-106">설명</span><span class="sxs-lookup"><span data-stu-id="327e6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="327e6-107">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-107">CreateBreakpoint Method</span></span>](icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="327e6-108">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-108">Not implemented.</span></span>|  
|[<span data-ttu-id="327e6-109">EnableClassLoadCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-109">EnableClassLoadCallbacks Method</span></span>](icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="327e6-110">이 모듈에 대해 [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) 및 [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) 콜백이 호출 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-110">Determines whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="327e6-111">EnableJITDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-111">EnableJITDebugging Method</span></span>](icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="327e6-112">JIT (just-in-time) 컴파일러에서이 모듈의 메서드에 대 한 디버깅 정보를 유지할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="327e6-113">GetAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-113">GetAssembly Method</span></span>](icordebugmodule-getassembly-method.md)|<span data-ttu-id="327e6-114">이 모듈에 대 한 포함 어셈블리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="327e6-115">GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-115">GetBaseAddress Method</span></span>](icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="327e6-116">모듈의 기본 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="327e6-117">GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-117">GetClassFromToken Method</span></span>](icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="327e6-118">메타 데이터에서 ICorDebugClass을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="327e6-119">GetEditAndContinueSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-119">GetEditAndContinueSnapshot Method</span></span>](icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="327e6-120">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-120">Deprecated.</span></span>|  
|[<span data-ttu-id="327e6-121">GetFunctionFromRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-121">GetFunctionFromRVA Method</span></span>](icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="327e6-122">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-122">Not implemented.</span></span>|  
|[<span data-ttu-id="327e6-123">GetFunctionFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-123">GetFunctionFromToken Method</span></span>](icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="327e6-124">메타 데이터 토큰에 의해 지정 된 함수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="327e6-125">GetGlobalVariableValue 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-125">GetGlobalVariableValue Method</span></span>](icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="327e6-126">지정 된 전역 변수에 대 한 값 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="327e6-127">GetMetaDataInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-127">GetMetaDataInterface Method</span></span>](icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="327e6-128">모듈에 대 한 메타 데이터를 검사 하는 데 사용할 수 있는 메타 데이터 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="327e6-129">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-129">GetName Method</span></span>](icordebugmodule-getname-method.md)|<span data-ttu-id="327e6-130">모듈의 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="327e6-131">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-131">GetProcess Method</span></span>](icordebugmodule-getprocess-method.md)|<span data-ttu-id="327e6-132">이 모듈에 대 한 프로세스를 포함 하는을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="327e6-133">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-133">GetSize Method</span></span>](icordebugmodule-getsize-method.md)|<span data-ttu-id="327e6-134">모듈의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="327e6-135">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-135">GetToken Method</span></span>](icordebugmodule-gettoken-method.md)|<span data-ttu-id="327e6-136">이 모듈의 테이블 항목에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="327e6-137">IsDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-137">IsDynamic Method</span></span>](icordebugmodule-isdynamic-method.md)|<span data-ttu-id="327e6-138">모듈이 동적 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="327e6-139">IsInMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="327e6-139">IsInMemory Method</span></span>](icordebugmodule-isinmemory-method.md)|<span data-ttu-id="327e6-140">이 모듈이 메모리에만 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="327e6-141">설명</span><span class="sxs-lookup"><span data-stu-id="327e6-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="327e6-142">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="327e6-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="327e6-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="327e6-143">Requirements</span></span>  

 <span data-ttu-id="327e6-144">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="327e6-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="327e6-145">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="327e6-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="327e6-146">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="327e6-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="327e6-147">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="327e6-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327e6-148">참조</span><span class="sxs-lookup"><span data-stu-id="327e6-148">See also</span></span>

- [<span data-ttu-id="327e6-149">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="327e6-149">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="327e6-150">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="327e6-150">Debugging Interfaces</span></span>](debugging-interfaces.md)
