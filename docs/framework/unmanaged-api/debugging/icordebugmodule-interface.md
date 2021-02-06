---
description: '자세히 알아보기: ICorDebugModule 인터페이스'
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
ms.openlocfilehash: f78023fe9975b609309c1c511380a3a394426283
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660117"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="e90e5-103">ICorDebugModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e90e5-103">ICorDebugModule Interface</span></span>

<span data-ttu-id="e90e5-104">실행 파일 또는 DLL (동적 연결 라이브러리) 인 CLR (공용 언어 런타임) 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-104">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e90e5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-105">Methods</span></span>  
  
|<span data-ttu-id="e90e5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-106">Method</span></span>|<span data-ttu-id="e90e5-107">설명</span><span class="sxs-lookup"><span data-stu-id="e90e5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e90e5-108">CreateBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-108">CreateBreakpoint Method</span></span>](icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="e90e5-109">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-109">Not implemented.</span></span>|  
|[<span data-ttu-id="e90e5-110">EnableClassLoadCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-110">EnableClassLoadCallbacks Method</span></span>](icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="e90e5-111">이 모듈에 대해 [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) 및 [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) 콜백이 호출 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-111">Determines whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="e90e5-112">EnableJITDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-112">EnableJITDebugging Method</span></span>](icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="e90e5-113">JIT (just-in-time) 컴파일러에서이 모듈의 메서드에 대 한 디버깅 정보를 유지할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-113">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="e90e5-114">GetAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-114">GetAssembly Method</span></span>](icordebugmodule-getassembly-method.md)|<span data-ttu-id="e90e5-115">이 모듈에 대 한 포함 어셈블리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-115">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="e90e5-116">GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-116">GetBaseAddress Method</span></span>](icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="e90e5-117">모듈의 기본 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-117">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="e90e5-118">GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-118">GetClassFromToken Method</span></span>](icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="e90e5-119">메타 데이터에서 ICorDebugClass을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-119">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="e90e5-120">GetEditAndContinueSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-120">GetEditAndContinueSnapshot Method</span></span>](icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="e90e5-121">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-121">Deprecated.</span></span>|  
|[<span data-ttu-id="e90e5-122">GetFunctionFromRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-122">GetFunctionFromRVA Method</span></span>](icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="e90e5-123">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-123">Not implemented.</span></span>|  
|[<span data-ttu-id="e90e5-124">GetFunctionFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-124">GetFunctionFromToken Method</span></span>](icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="e90e5-125">메타 데이터 토큰에 의해 지정 된 함수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-125">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="e90e5-126">GetGlobalVariableValue 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-126">GetGlobalVariableValue Method</span></span>](icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="e90e5-127">지정 된 전역 변수에 대 한 값 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-127">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="e90e5-128">GetMetaDataInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-128">GetMetaDataInterface Method</span></span>](icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="e90e5-129">모듈에 대 한 메타 데이터를 검사 하는 데 사용할 수 있는 메타 데이터 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-129">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="e90e5-130">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-130">GetName Method</span></span>](icordebugmodule-getname-method.md)|<span data-ttu-id="e90e5-131">모듈의 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-131">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="e90e5-132">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-132">GetProcess Method</span></span>](icordebugmodule-getprocess-method.md)|<span data-ttu-id="e90e5-133">이 모듈에 대 한 프로세스를 포함 하는을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-133">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="e90e5-134">GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-134">GetSize Method</span></span>](icordebugmodule-getsize-method.md)|<span data-ttu-id="e90e5-135">모듈의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-135">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="e90e5-136">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-136">GetToken Method</span></span>](icordebugmodule-gettoken-method.md)|<span data-ttu-id="e90e5-137">이 모듈의 테이블 항목에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-137">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="e90e5-138">IsDynamic 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-138">IsDynamic Method</span></span>](icordebugmodule-isdynamic-method.md)|<span data-ttu-id="e90e5-139">모듈이 동적 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-139">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="e90e5-140">IsInMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="e90e5-140">IsInMemory Method</span></span>](icordebugmodule-isinmemory-method.md)|<span data-ttu-id="e90e5-141">이 모듈이 메모리에만 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-141">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e90e5-142">설명</span><span class="sxs-lookup"><span data-stu-id="e90e5-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e90e5-143">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e90e5-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e90e5-144">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e90e5-144">Requirements</span></span>  

 <span data-ttu-id="e90e5-145">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e90e5-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e90e5-146">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e90e5-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e90e5-147">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e90e5-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e90e5-148">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e90e5-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e90e5-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e90e5-149">See also</span></span>

- [<span data-ttu-id="e90e5-150">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e90e5-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="e90e5-151">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e90e5-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
