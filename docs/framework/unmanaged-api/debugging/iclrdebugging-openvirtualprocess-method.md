---
title: ICLRDebugging::OpenVirtualProcess 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a313ea62455067fb36b94d942b0ce21589677e3b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122579"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="80130-102">ICLRDebugging::OpenVirtualProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="80130-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="80130-103">프로세스에 로드 된 공용 언어 런타임 (CLR) 모듈에 해당 하는 ICorDebugProcess 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="80130-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80130-104">구문</span><span class="sxs-lookup"><span data-stu-id="80130-104">Syntax</span></span>  
  
```  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80130-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="80130-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="80130-106">[in] 대상 프로세스에서 모듈의 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="80130-107">지정된 된 모듈이 CLR 모듈이 없으면 COR_E_NOT_CLR 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="80130-108">[in] 데이터 대상 추상화를 관리 되는 경우 디버거가 프로세스 상태를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="80130-109">디버거를 구현 해야 합니다 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-109">The debugger must implement the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="80130-110">구현 해야 합니다 [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) 디버깅 중인 CLR 설치 되지 않은 로컬 컴퓨터의 시나리오를 지원 하도록 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-110">You should implement the [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="80130-111">[in] 버전별 디버깅 라이브러리 있고에 로드 된 요청 수를 허용 하는 라이브러리 공급자 콜백 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="80130-112">경우에이 매개 변수는 필수 `ppProcess` 나 `pFlags` 아닙니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="80130-113">[in] 이 디버거를 디버깅할 수는 CLR의 가장 높은 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="80130-114">주, 부를 지정 하 고 및 빌드 버전을 디버거에서이 CLR 최신 하 고, 수정 번호 서비스 릴리스 이후 전체 CLR을 수용 하기 위해 65535로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="80130-115">[in] 검색할 ICorDebugProcess 인터페이스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="80130-116">현재 허용 되는 유일한 값은 IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, 및 IID_CORDEBUGPROCESS 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="80130-117">[out] 로 식별 되는 COM 인터페이스에 대 한 포인터 `riidProcess`합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="80130-118">[out에서] CLR의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="80130-119">이 값은 입력에 대해 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-119">On input, this value can be `null`.</span></span> <span data-ttu-id="80130-120">가리킬 수도 있습니다는 [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) 구조체의 경우에서 구조체 `wStructVersion` 필드를 0 (영)으로 초기화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-120">It can also point to a [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="80130-121">반환된 된 출력에서 `CLR_DEBUGGING_VERSION` 구조 CLR의 버전 정보를 사용 하 여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="80130-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="80130-122">[out] 지정 된 런타임에 대 한 정보 제공 용 이므로 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="80130-123">참조 된 [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) 플래그에 대 한 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80130-124">반환 값</span><span class="sxs-lookup"><span data-stu-id="80130-124">Return Value</span></span>  
 <span data-ttu-id="80130-125">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="80130-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80130-126">HRESULT</span></span>|<span data-ttu-id="80130-127">설명</span><span class="sxs-lookup"><span data-stu-id="80130-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80130-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="80130-128">S_OK</span></span>|<span data-ttu-id="80130-129">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="80130-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="80130-130">E_POINTER</span></span>|`pDataTarget` <span data-ttu-id="80130-131">`null`합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-131">is `null`.</span></span>|  
|<span data-ttu-id="80130-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="80130-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="80130-133">합니다 [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) 콜백 오류를 반환 하거나 유효한 핸들을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-133">The [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="80130-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="80130-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|`pDataTarget` <span data-ttu-id="80130-135">이 버전의 런타임이 필요한 데이터 대상 인터페이스를 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-135">does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="80130-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="80130-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="80130-137">표시 된 모듈이 CLR 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="80130-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="80130-138">메모리가 손상, 모듈을 사용할 수 없는 CLR 버전은 shim 된 버전 보다 최신 때문에 CLR 모듈을 검색할 수 없는 경우에이 HRESULT 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="80130-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="80130-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="80130-140">이 런타임 버전에서이 디버깅 모델을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="80130-141">현재, 모델을 디버깅 하기 전에 CLR 버전에서 지원 되지 않습니다는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-141">Currently, the debugging model is not supported by CLR versions before the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="80130-142">`pwszVersion` 출력 매개 변수는 여전히이 오류 후 올바른 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="80130-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="80130-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="80130-144">버전의 CLR이 디버거에서 지원 해야 하는 버전 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="80130-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="80130-145">`pwszVersion` 출력 매개 변수는 여전히이 오류 후 올바른 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80130-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="80130-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="80130-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="80130-147">`riidProcess` 인터페이스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80130-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="80130-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="80130-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="80130-149">합니다 `CLR_DEBUGGING_VERSION` 구조에 대 한 인식 된 값이 없는 `wStructVersion`합니다.</span><span class="sxs-lookup"><span data-stu-id="80130-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="80130-150">이 이번에 허용 되는 유일한 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="80130-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="80130-151">예외</span><span class="sxs-lookup"><span data-stu-id="80130-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80130-152">설명</span><span class="sxs-lookup"><span data-stu-id="80130-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80130-153">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80130-153">Requirements</span></span>  
 <span data-ttu-id="80130-154">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="80130-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80130-155">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80130-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80130-156">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80130-156">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="80130-157">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="80130-157">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80130-158">참고자료</span><span class="sxs-lookup"><span data-stu-id="80130-158">See also</span></span>

- [<span data-ttu-id="80130-159">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80130-159">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="80130-160">디버깅</span><span class="sxs-lookup"><span data-stu-id="80130-160">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
