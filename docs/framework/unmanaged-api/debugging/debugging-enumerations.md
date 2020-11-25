---
title: 디버깅 열거형
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: bdd4b60d068677ae2a0874b589294ba220f0d854
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723001"
---
# <a name="debugging-enumerations"></a><span data-ttu-id="484fd-102">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-102">Debugging Enumerations</span></span>

<span data-ttu-id="484fd-103">이 섹션에서는 디버깅 API에서 사용하는 관리되지 않는 열거형에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="484fd-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="484fd-104">In This Section</span></span>  

 [<span data-ttu-id="484fd-105">CLR_DEBUGGING_PROCESS_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="484fd-106">[ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) 메서드에서 사용 하는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="484fd-107">CLRDataEnumMemoryFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-107">CLRDataEnumMemoryFlags Enumeration</span></span>](clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="484fd-108">[ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) 메서드에 대 한 호출에 포함 되어야 하는 메모리 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="484fd-109">COR_PUB_ENUMPROCESS 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="484fd-110">열거할 프로세스 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="484fd-111">CorDebugBlockingReason 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-111">CorDebugBlockingReason Enumeration</span></span>](cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="484fd-112">지정된 개체에서 스레드가 차단될 수 있는 이유를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="484fd-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="484fd-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="484fd-114">호출 체인의 시작 이유를 하나 이상 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="484fd-115">CorDebugCodeInvokeKind 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-115">CorDebugCodeInvokeKind Enumeration</span></span>](cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="484fd-116">내보낸 함수가 관리 코드를 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="484fd-117">CorDebugCodeInvokePurpose 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-117">CorDebugCodeInvokePurpose Enumeration</span></span>](cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="484fd-118">내보낸 함수가 관리 코드를 호출하는 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="484fd-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="484fd-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="484fd-120">[ICorDebug:: CreateProcess](icordebug-createprocess-method.md) 메서드 호출에 사용할 수 있는 추가 디버깅 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="484fd-121">CorDebugDebugEventKind 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-121">CorDebugDebugEventKind Enumeration</span></span>](cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="484fd-122">[DecodeEvent](icordebugprocess6-decodeevent-method.md) 메서드가 정보를 디코딩하는 이벤트의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-122">Indicates the type of event whose information is decoded by the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="484fd-123">CorDebugDecodeEventFlagsWindows 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="484fd-124">Windows 플랫폼에서 디버그 이벤트에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="484fd-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="484fd-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="484fd-126">[ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) 이벤트에서 생성 된 콜백의 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="484fd-127">CorDebugExceptionFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-127">CorDebugExceptionFlags Enumeration</span></span>](cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="484fd-128">예외에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="484fd-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="484fd-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="484fd-130">해제 단계 중에 콜백에서 신호를 보내는 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="484fd-131">CorDebugGCType 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-131">CorDebugGCType Enumeration</span></span>](cordebuggctype-enumeration.md)  
 <span data-ttu-id="484fd-132">가비지 수집기가 실행되고 있는 위치(워크스테이션 또는 서버)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="484fd-133">CorDebugGenerationTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-133">CorDebugGenerationTypes Enumeration</span></span>](cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="484fd-134">관리되는 힙에 대한 메모리 영역 생성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="484fd-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="484fd-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="484fd-136">핸들 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="484fd-137">CorDebugIlToNativeMappingTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="484fd-138">기본 명령의 특정 범위가 특수 코드 영역에 해당하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="484fd-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="484fd-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="484fd-140">한 단계씩 실행할 수 있는 코드 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="484fd-141">CorDebugInterfaceVersion 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-141">CorDebugInterfaceVersion Enumeration</span></span>](cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="484fd-142">특정 .NET Framework 버전 또는 인터페이스가 적용된 .NET Framework 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="484fd-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="484fd-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="484fd-144">스택 프레임 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="484fd-145">CorDebugJITCompilerFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-145">CorDebugJITCompilerFlags Enumeration</span></span>](cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="484fd-146">관리되는 JIT(Just-In-Time) 컴파일러의 동작에 영향을 주는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="484fd-147">CorDebugJITCompilerFlagsDeprecated 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="484fd-148">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-148">Obsolete.</span></span> <span data-ttu-id="484fd-149">`CORDEBUG_JIT_DEFAULT`대신 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형의 멤버를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="484fd-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="484fd-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="484fd-151">IP(명령 포인터)의 값을 가져온 방법에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="484fd-152">CorDebugMDAFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-152">CorDebugMDAFlags Enumeration</span></span>](cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="484fd-153">MDA(관리 디버깅 도우미)가 실행된 스레드의 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="484fd-154">CorDebugNGenPolicy 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-154">CorDebugNGenPolicy Enumeration</span></span>](cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="484fd-155">디버거가 네이티브 이미지 캐시에서 네이티브(NGen) 이미지를 로드하는지 여부를 결정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="484fd-156">CorDebugPlatform 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-156">CorDebugPlatform Enumeration</span></span>](cordebugplatform-enumeration.md)  
 <span data-ttu-id="484fd-157">[ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) 메서드에서 사용 하는 대상 플랫폼 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="484fd-158">CorDebugRecordFormat 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-158">CorDebugRecordFormat Enumeration</span></span>](cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="484fd-159">네이티브 예외 디버그 이벤트에 대한 정보가 포함된 바이트 배열의 데이터 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="484fd-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="484fd-160">CorDebugRegister</span></span>  
 <span data-ttu-id="484fd-161">지정한 프로세서 아키텍처에 연결된 레지스터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="484fd-162">CorDebugSetContextFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-162">CorDebugSetContextFlag Enumeration</span></span>](cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="484fd-163">컨텍스트가 스택의 활성(리프) 프레임에서 가져온 것인지 아니면 다른 프레임에서 해제하여 계산되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="484fd-164">CorDebugStateChange 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-164">CorDebugStateChange Enumeration</span></span>](cordebugstatechange-enumeration.md)  
 <span data-ttu-id="484fd-165">프로세스에 대한 변경 내용을 기반으로 삭제해야 하는 캐시된 데이터의 양을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="484fd-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="484fd-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="484fd-167">개별 단계의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="484fd-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="484fd-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="484fd-169">디버깅을 위한 스레드 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="484fd-170">\>CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="484fd-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="484fd-171">스텝퍼에 의해 코드 실행에서 중지를 트리거할 수 있는 매핑되지 않은 코드 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="484fd-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="484fd-172">CorDebugUserState</span></span>  
 <span data-ttu-id="484fd-173">스레드의 사용자 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="484fd-174">CorGCReferenceType 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-174">CorGCReferenceType Enumeration</span></span>](corgcreferencetype-enumeration.md)  
 <span data-ttu-id="484fd-175">가비지가 수집될 개체의 소스를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="484fd-176">ILCodeKind 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-176">ILCodeKind Enumeration</span></span>](ilcodekind-enumeration.md)  
 <span data-ttu-id="484fd-177">디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수나 코드에 액세스할 수 있는지 여부를 지정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="484fd-178">LoggingLevelEnum 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-178">LoggingLevelEnum Enumeration</span></span>](logginglevelenum-enumeration.md)  
 <span data-ttu-id="484fd-179">관리되는 스레드가 이벤트를 기록할 때 이벤트 로그에 기록되는 설명 메시지의 보안 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="484fd-180">LogSwitchCallReason 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-180">LogSwitchCallReason Enumeration</span></span>](logswitchcallreason-enumeration.md)  
 <span data-ttu-id="484fd-181">디버깅/추적 스위치에 대해 수행된 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="484fd-182">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-182">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)  
 <span data-ttu-id="484fd-183">변수의 기본 위치 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="484fd-184">WriteableMetadataUpdateMode 열거형</span><span class="sxs-lookup"><span data-stu-id="484fd-184">WriteableMetadataUpdateMode Enumeration</span></span>](writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="484fd-185">메타데이터에 대한 메모리 내 업데이트가 디버거에 표시되는지 여부를 지정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>

 <span data-ttu-id="484fd-186">[ClrDataSourceType 열거형](clrdatasourcetype-enumeration.md) CLRDATA_IL_ADDRESS_MAP 구조체에서 사용 되는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="484fd-186">[ClrDataSourceType Enumeration](clrdatasourcetype-enumeration.md) Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="484fd-187">관련 단원</span><span class="sxs-lookup"><span data-stu-id="484fd-187">Related Sections</span></span>  

 [<span data-ttu-id="484fd-188">디버깅 Coclass</span><span class="sxs-lookup"><span data-stu-id="484fd-188">Debugging Coclasses</span></span>](debugging-coclasses.md)  
  
 [<span data-ttu-id="484fd-189">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="484fd-189">Debugging Interfaces</span></span>](debugging-interfaces.md)  
  
 [<span data-ttu-id="484fd-190">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="484fd-190">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)  
  
 [<span data-ttu-id="484fd-191">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="484fd-191">Debugging Structures</span></span>](debugging-structures.md)
