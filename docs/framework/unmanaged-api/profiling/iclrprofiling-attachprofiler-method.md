---
description: '자세히 알아보기: ICLRProfiling:: AttachProfiler 메서드'
title: ICLRProfiling::AttachProfiler 메서드
ms.date: 03/30/2017
api_name:
- IClrProfiling.AttachProfiler Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- IClrProfiling::AttachProfiler
helpviewer_keywords:
- AttachProfiler method [.NET Framework profiling]
- IClrProfiling::AttachProfiler method [.NET Framework profiling]
ms.assetid: 535a6839-c443-405b-a6f4-e2af90725d5b
topic_type:
- apiref
ms.openlocfilehash: 00ae5ca76462d8800a77c2869ef73703a4f1d980
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760771"
---
# <a name="iclrprofilingattachprofiler-method"></a><span data-ttu-id="64d67-103">ICLRProfiling::AttachProfiler 메서드</span><span class="sxs-lookup"><span data-stu-id="64d67-103">ICLRProfiling::AttachProfiler Method</span></span>

<span data-ttu-id="64d67-104">지정한 프로파일러를 지정된 프로세스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-104">Attaches the specified profiler to the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d67-105">구문</span><span class="sxs-lookup"><span data-stu-id="64d67-105">Syntax</span></span>  
  
```cpp  
HRESULT AttachProfiler(  
  [in] DWORD dwProfileeProcessID,  
  [in] DWORD dwMillisecondsMax,                     // optional  
  [in] const CLSID * pClsidProfiler,  
  [in] LPCWSTR wszProfilerPath,                     // optional  
  [in] size_is(cbClientData)] void * pvClientData,  // optional  
  [in] UINT cbClientData);                          // optional  
```  
  
## <a name="parameters"></a><span data-ttu-id="64d67-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64d67-106">Parameters</span></span>

<span data-ttu-id="64d67-107">`dwProfileeProcessID` 진행 프로파일러를 연결 해야 하는 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-107">`dwProfileeProcessID` [in] The process ID of the process to which the profiler should be attached.</span></span> <span data-ttu-id="64d67-108">64비트 컴퓨터에서는 프로파일링된 프로세스의 비트가 `AttachProfiler`를 호출하는 트리거 프로세스의 비트와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-108">On a 64-bit machine, the profiled process's bitness must match the bitness of the trigger process that is calling `AttachProfiler`.</span></span> <span data-ttu-id="64d67-109">`AttachProfiler`가 호출되는 사용자 계정에 관리 권한이 있는 경우 대상 프로세스는 시스템의 모든 프로세스일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-109">If the user account under which `AttachProfiler` is called has administrative privileges, the target process may be any process on the system.</span></span> <span data-ttu-id="64d67-110">그러지 않으면 대상 프로세스가 동일한 사용자 계정에 의해 소유되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-110">Otherwise, the target process must be owned by the same user account.</span></span>

<span data-ttu-id="64d67-111">`dwMillisecondsMax` 진행 이 완료 될 때 까지의 시간 기간 (밀리초) `AttachProfiler` 입니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-111">`dwMillisecondsMax` [in] The time duration, in milliseconds, for `AttachProfiler` to complete.</span></span> <span data-ttu-id="64d67-112">트리거 프로세스는 특정 프로파일러가 초기화를 완료하기에 충분한 것으로 알려진 시간 제한을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-112">The trigger process should pass a timeout that is known to be sufficient for the particular profiler to complete its initialization.</span></span>
  
<span data-ttu-id="64d67-113">`pClsidProfiler` 진행 로드할 프로파일러의 CLSID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-113">`pClsidProfiler` [in] A pointer to the CLSID of the profiler to be loaded.</span></span> <span data-ttu-id="64d67-114">트리거 프로세스는 `AttachProfiler`가 반환된 후 이 메모리를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-114">The trigger process can reuse this memory after `AttachProfiler` returns.</span></span>

<span data-ttu-id="64d67-115">`wszProfilerPath` 진행 로드할 프로파일러 DLL 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-115">`wszProfilerPath` [in] The full path to the profiler’s DLL file to be loaded.</span></span> <span data-ttu-id="64d67-116">이 문자열에는 null 종결자를 포함하여 260자 이하가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-116">This string should contain no more than 260 characters, including the null terminator.</span></span> <span data-ttu-id="64d67-117">`wszProfilerPath`가 null 또는 빈 문자열인 경우 CLR(공용 언어 런타임)은 `pClsidProfiler`가 가리키는 CLSID를 레지스트리에서 찾아 프로파일러 DLL 파일의 위치를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-117">If `wszProfilerPath` is null or an empty string, the common language runtime (CLR) will try to find the location of the profiler’s DLL file by looking in the registry for the CLSID that `pClsidProfiler` points to.</span></span>

<span data-ttu-id="64d67-118">`pvClientData` 진행 [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) 메서드로 프로파일러에 전달 될 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-118">`pvClientData` [in] A pointer to data to be passed to the profiler by the [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method.</span></span> <span data-ttu-id="64d67-119">트리거 프로세스는 `AttachProfiler`가 반환된 후 이 메모리를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-119">The trigger process can reuse this memory after `AttachProfiler` returns.</span></span> <span data-ttu-id="64d67-120">`pvClientData`가 null이면 `cbClientData`는 0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-120">If `pvClientData` is null, `cbClientData` must be 0 (zero).</span></span>

<span data-ttu-id="64d67-121">`cbClientData` 진행 가 가리키는 데이터의 크기 (바이트)입니다 `pvClientData` .</span><span class="sxs-lookup"><span data-stu-id="64d67-121">`cbClientData` [in] The size, in bytes, of the data that `pvClientData` points to.</span></span>

## <a name="return-value"></a><span data-ttu-id="64d67-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="64d67-122">Return Value</span></span>  

 <span data-ttu-id="64d67-123">이 메서드는 다음과 같은 HRESULT를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-123">This method returns the following HRESULTs.</span></span>  
  
|<span data-ttu-id="64d67-124">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64d67-124">HRESULT</span></span>|<span data-ttu-id="64d67-125">설명</span><span class="sxs-lookup"><span data-stu-id="64d67-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64d67-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="64d67-126">S_OK</span></span>|<span data-ttu-id="64d67-127">지정된 프로파일러가 대상 프로세스에 성공적으로 연결했습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-127">The specified profiler has successfully attached to the target process.</span></span>|  
|<span data-ttu-id="64d67-128">CORPROF_E_PROFILER_ALREADY_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="64d67-128">CORPROF_E_PROFILER_ALREADY_ACTIVE</span></span>|<span data-ttu-id="64d67-129">활성 상태이거나 대상 프로세스에 연결하는 프로파일러가 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-129">There is already a profiler active or attaching to the target process.</span></span>|  
|<span data-ttu-id="64d67-130">CORPROF_E_PROFILER_NOT_ATTACHABLE</span><span class="sxs-lookup"><span data-stu-id="64d67-130">CORPROF_E_PROFILER_NOT_ATTACHABLE</span></span>|<span data-ttu-id="64d67-131">지정된 프로파일러가 연결을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-131">The specified profiler does not support attachment.</span></span> <span data-ttu-id="64d67-132">트리거 프로세스가 다른 프로파일러를 연결하려고 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-132">The trigger process may attempt to attach a different profiler.</span></span>|  
|<span data-ttu-id="64d67-133">CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER</span><span class="sxs-lookup"><span data-stu-id="64d67-133">CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER</span></span>|<span data-ttu-id="64d67-134">대상 프로세스 버전이 `AttachProfiler`를 호출하는 현재 프로세스와 호환되지 않으므로 프로파일러 연결을 요청할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-134">Unable to request a profiler attachment, because the version of the target process is incompatible with the current process that is calling `AttachProfiler`.</span></span>|  
|<span data-ttu-id="64d67-135">HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)</span><span class="sxs-lookup"><span data-stu-id="64d67-135">HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)</span></span>|<span data-ttu-id="64d67-136">트리거 프로세스의 사용자에게 대상 프로세스에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-136">The user of the trigger process does not have access to the target process.</span></span>|  
|<span data-ttu-id="64d67-137">HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)</span><span class="sxs-lookup"><span data-stu-id="64d67-137">HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)</span></span>|<span data-ttu-id="64d67-138">트리거 프로세스의 사용자에게 프로파일러를 지정된 대상 프로세스에 연결하는 데 필요한 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-138">The user of the trigger process does not have the privileges necessary to attach a profiler to the given target process.</span></span> <span data-ttu-id="64d67-139">애플리케이션 이벤트 로그에 자세한 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-139">The application event log may contain more information.</span></span>|  
|<span data-ttu-id="64d67-140">CORPROF_E_IPC_FAILED</span><span class="sxs-lookup"><span data-stu-id="64d67-140">CORPROF_E_IPC_FAILED</span></span>|<span data-ttu-id="64d67-141">대상 프로세스와 통신할 때 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-141">A failure occurred when communicating with the target process.</span></span> <span data-ttu-id="64d67-142">이 문제는 일반적으로 대상 프로세스를 종료하는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-142">This commonly happens if the target process was shutting down.</span></span>|  
|<span data-ttu-id="64d67-143">HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="64d67-143">HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)</span></span>|<span data-ttu-id="64d67-144">대상 프로세스가 없거나 연결을 지원하는 CLR을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-144">The target process does not exist or is not running a CLR that supports attachment.</span></span> <span data-ttu-id="64d67-145">이는 런타임 열거형 메서드 호출 이후에 CLR가 언로드되었음을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-145">This may indicate that the CLR was unloaded since the call to the runtime enumeration method.</span></span>|  
|<span data-ttu-id="64d67-146">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span><span class="sxs-lookup"><span data-stu-id="64d67-146">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span></span>|<span data-ttu-id="64d67-147">프로파일러 로드를 시작하지 않고 시간 제한이 만료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-147">The timeout expired without beginning to load the profiler.</span></span> <span data-ttu-id="64d67-148">연결 작업을 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-148">You can retry the attach operation.</span></span> <span data-ttu-id="64d67-149">시간 초과는 대상 프로세스의 종료자가 시간 제한 값보다 오래 실행되는 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-149">Timeouts occur when a finalizer in the target process runs for a longer time than the timeout value.</span></span>|  
|<span data-ttu-id="64d67-150">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="64d67-150">E_INVALIDARG</span></span>|<span data-ttu-id="64d67-151">하나 이상의 매개 변수에 잘못된 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-151">One or more parameters have invalid values.</span></span>|  
|<span data-ttu-id="64d67-152">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64d67-152">E_FAIL</span></span>|<span data-ttu-id="64d67-153">지정되지 않은 다른 일부 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-153">Some other, unspecified failure occurred.</span></span>|  
|<span data-ttu-id="64d67-154">기타 오류 코드</span><span class="sxs-lookup"><span data-stu-id="64d67-154">Other error codes</span></span>|<span data-ttu-id="64d67-155">프로파일러의 [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) 메서드가 실패를 나타내는 hresult를 반환 하는 경우 `AttachProfiler` 는 동일한 hresult를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-155">If the profiler’s [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method returns an HRESULT that indicates failure, `AttachProfiler` returns that same HRESULT.</span></span> <span data-ttu-id="64d67-156">이 경우 E_NOTIMPL이 CORPROF_E_PROFILER_NOT_ATTACHABLE로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-156">In this case, E_NOTIMPL is converted to CORPROF_E_PROFILER_NOT_ATTACHABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64d67-157">설명</span><span class="sxs-lookup"><span data-stu-id="64d67-157">Remarks</span></span>  
  
## <a name="memory-management"></a><span data-ttu-id="64d67-158">메모리 관리</span><span class="sxs-lookup"><span data-stu-id="64d67-158">Memory Management</span></span>  

 <span data-ttu-id="64d67-159">COM 규칙에 따라 `AttachProfiler` 호출자(예: 프로파일러 개발자가 작성한 트리거 코드)는 `pvClientData` 매개 변수가 가리키는 데이터에 대한 메모리를 할당 및 할당 취소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-159">In keeping with COM conventions, the caller of `AttachProfiler` (for example, the trigger code authored by the profiler developer) is responsible for allocating and de-allocating the memory for the data that the `pvClientData` parameter points to.</span></span> <span data-ttu-id="64d67-160">CLR은 `AttachProfiler` 호출을 실행할 때 `pvClientData`가 가리키는 메모리의 복사본을 만들고 대상 프로세스에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-160">When the CLR executes the `AttachProfiler` call, it makes a copy of the memory that `pvClientData` points to and transmits it to the target process.</span></span> <span data-ttu-id="64d67-161">대상 프로세스 내의 CLR이 고유한 `pvClientData` 블록 복사본을 받으면 `InitializeForAttach` 메서드를 통해 블록을 프로파일러에 전달한 다음 대상 프로세스에서 `pvClientData` 블록 복사본의 할당을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="64d67-161">When the CLR inside the target process receives its own copy of the `pvClientData` block, it passes the block to the profiler through the `InitializeForAttach` method, and then deallocates its copy of the `pvClientData` block from the target process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64d67-162">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64d67-162">Requirements</span></span>  

 <span data-ttu-id="64d67-163">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="64d67-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64d67-164">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64d67-164">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64d67-165">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64d67-165">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64d67-166">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64d67-166">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d67-167">참조</span><span class="sxs-lookup"><span data-stu-id="64d67-167">See also</span></span>

- [<span data-ttu-id="64d67-168">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64d67-168">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="64d67-169">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64d67-169">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="64d67-170">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64d67-170">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="64d67-171">프로파일링</span><span class="sxs-lookup"><span data-stu-id="64d67-171">Profiling</span></span>](index.md)
