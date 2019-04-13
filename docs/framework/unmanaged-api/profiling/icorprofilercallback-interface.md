---
title: ICorProfilerCallback 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback
helpviewer_keywords:
- ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2f474317493b3aac421ca1270ff461b97cfe027
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125946"
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback 인터페이스
코드 프로파일러는 프로파일러가 구독 한 이벤트가 발생할 때 알릴는 CLR (공용 언어 런타임)에서 사용 되는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[AppDomainCreationFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|응용 프로그램 도메인이 만들어졌는지 프로파일러에 알립니다.|  
|[AppDomainCreationStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|응용 프로그램 도메인은 생성 되 고 있음을 프로파일러에 알립니다.|  
|[AppDomainShutdownFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|응용 프로그램 도메인을 프로세스에서 로드 되었음을 프로파일러에 알립니다.|  
|[AppDomainShutdownStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|프로세스에서 응용 프로그램 도메인이 언로드되고 있음을 프로파일러에 알립니다.|  
|[AssemblyLoadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|어셈블리 로드 되었음을 프로파일러에 알립니다.|  
|[AssemblyLoadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|어셈블리 로드 되는 프로파일러에 알립니다.|  
|[AssemblyUnloadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|어셈블리 로드 되었음을 프로파일러에 알립니다.|  
|[AssemblyUnloadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|어셈블리를 언로드되고 있음을 프로파일러에 알립니다.|  
|[ClassLoadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|클래스 로드 되었음을 프로파일러에 알립니다.|  
|[ClassLoadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|클래스 로드 되는 프로파일러에 알립니다.|  
|[ClassUnloadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|클래스 언로드 되었음을 프로파일러에 알립니다.|  
|[ClassUnloadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|클래스를 언로드되고 있음을 프로파일러에 알립니다.|  
|[COMClassicVTableCreated 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|런타임 호출 가능 래퍼 (RCW)를 지정 하는 IID 및 클래스에 대 한 만들어졌는지 프로파일러에 알립니다.|  
|[COMClassicVTableDestroyed 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|RCW 소멸 되 고 프로파일러에 알립니다.|  
|[ExceptionCatcherEnter 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|컨트롤을 적절 한 전달 되는 프로파일러에 알립니다 `catch` 블록입니다.|  
|[ExceptionCatcherLeave 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|컨트롤에서 적절 한 전달 되는 프로파일러에 알립니다 `catch` 블록입니다.|  
|[ExceptionCLRCatcherExecute 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|.NET Framework 버전 2.0에서에서 사용 되지 않음.|  
|[ExceptionCLRCatcherFound 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|.NET Framework 2.0에서에서 사용 되지 않음.|  
|[ExceptionOSHandlerEnter 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|구현되지 않았습니다. 관리 되지 않는 예외 정보를 필요로 하는 프로파일러는 다른 수단을 통해이 정보를 얻어야 합니다.|  
|[ExceptionOSHandlerLeave 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|구현되지 않았습니다. 관리 되지 않는 예외 정보를 필요로 하는 프로파일러는 다른 수단을 통해이 정보를 얻어야 합니다.|  
|[ExceptionSearchCatcherFound 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|예외 처리의 검색 단계에서 throw 된 예외에 대 한 처리기가 있는 프로파일러에 알립니다.|  
|[ExceptionSearchFilterEnter 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|사용자 필터가 실행 되는 프로파일러에 알립니다.|  
|[ExceptionSearchFilterLeave 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|사용자 필터를 방금 실행을 마친 프로파일러에 알립니다.|  
|[ExceptionSearchFunctionEnter 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|예외 처리의 검색 단계가 함수를 입력 했는지 프로파일러에 알립니다.|  
|[ExceptionSearchFunctionLeave 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|예외 처리의 검색 단계 함수 검색 되었음을 프로파일러에 알립니다.|  
|[ExceptionThrown 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|예외가 throw 되는 프로파일러에 알립니다.|  
|[ExceptionUnwindFinallyEnter 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|예외 해제 단계 처리를 입력 하는 프로파일러에 알립니다는 `finally` 지정된 된 함수에 포함 된 절.|  
|[ExceptionUnwindFinallyLeave 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|해제 단계 예외 처리에 남아 있는 프로파일러에 알립니다는 `finally` 절.|  
|[ExceptionUnwindFunctionEnter 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|예외 처리의 해제 단계가 함수를 입력 했는지 프로파일러에 알립니다.|  
|[ExceptionUnwindFunctionLeave 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|예외 처리의 해제 단계 함수 해제 되었음을 프로파일러에 알립니다.|  
|[FunctionUnloadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|런타임 함수를 언로드할 시작한는 프로파일러에 알립니다.|  
|[Initialize 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|새 CLR 응용 프로그램을 시작할 때 프로파일러를 초기화 하기 위해 호출 됩니다.|  
|[JITCachedFunctionSearchFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|이전에 NGen.exe를 사용 하 여 컴파일된 함수에 대 한 검색 되었음을 프로파일러에 알립니다.|  
|[JITCachedFunctionSearchStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|이전에 NGen.exe를 사용 하 여 컴파일된 함수에 대 한 검색이 시작는 프로파일러에 알립니다.|  
|[JITCompilationFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|JIT 컴파일러가 함수 컴파일이 되었음을 프로파일러에 알립니다.|  
|[JITCompilationStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Just-in-time (JIT) 컴파일러에서 함수 컴파일을 시작 했다는 프로파일러에 알립니다.|  
|[JITFunctionPitched 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|JIT 컴파일 된 함수 메모리에서 제거 되었습니다 프로파일러에 알립니다.|  
|[JITInlining 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|다른 함수에 따라 함수를 삽입할 JIT 컴파일러는 프로파일러에 알립니다.|  
|[ManagedToUnmanagedTransition 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|관리 코드에서 비관리 코드로 전환 되었음을 프로파일러에 알립니다.|  
|[ModuleAttachedToAssembly 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|모듈 부모 어셈블리에 연결 되는 프로파일러에 알립니다.|  
|[ModuleLoadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|모듈 로드 되었음을 프로파일러에 알립니다.|  
|[ModuleLoadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|모듈 로드 되는 프로파일러에 알립니다.|  
|[ModuleUnloadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|모듈 언로드 되었음을 프로파일러에 알립니다.|  
|[ModuleUnloadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|모듈은 언로드됩니다 프로파일러에 알립니다.|  
|[MovedReferences 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|가비지 수집 중 이동 된 개체 참조에 대 한 프로파일러를 알립니다.|  
|[ObjectAllocated 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|개체에 대 한 할당 된 힙에 메모리 프로파일러에 알립니다.|  
|[ObjectReferences 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|지정된 된 개체에서 참조 하는 메모리에서 개체에 대 한 프로파일러를 알립니다.|  
|[ObjectsAllocatedByClass 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|이전 가비지 수집 이후 생성 된 각 지정 된 클래스의 인스턴스 수에 대 한 프로파일러를 알립니다.|  
|[RemotingClientInvocationFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|클라이언트에서 원격 호출이 완료 될 때까지 실행 된 프로파일러에 알립니다.|  
|[RemotingClientInvocationStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|원격 호출을 시작한 프로파일러에 알립니다.|  
|[RemotingClientReceivingReply 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|원격 호출의 서버 쪽 부분을 완료 하 고 클라이언트는 수신 하는 프로파일러에 알립니다 회신을 처리 하려고 하 고 있습니다.|  
|[RemotingClientSendingMessage 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|클라이언트가 서버 요청을 보내는 지 프로파일러에 알립니다.|  
|[RemotingServerInvocationReturned 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|프로세스에서 원격 메서드 호출 요청에 대 한 응답에서 메서드를 호출 되었음을 프로파일러에 알립니다.|  
|[RemotingServerInvocationStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|프로세스에서 원격 메서드 호출 요청에 대 한 응답에서 메서드를 호출 하는 프로파일러에 알립니다.|  
|[RemotingServerReceivingMessage 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|프로세스를 원격 메서드 호출 또는 정품 인증 요청을 수신 하는 프로파일러에 알립니다.|  
|[RemotingServerSendingReply 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|프로세스에서 원격 메서드 호출 요청 처리를 완료 하 고 채널을 통해 회신을 전송 하려고 프로파일러에 알립니다.|  
|[RootReferences 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|가비지 컬렉션 후 루트 참조에 대 한 정보를 사용 하 여 프로파일러를 알립니다.|  
|[RuntimeResumeFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|모든 런타임 스레드를 다시 시작 했습니다 런타임과 정상 작업 상태로 반환 되는 프로파일러에 알립니다.|  
|[RuntimeResumeStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|런타임은 모든 런타임 스레드가 다시 시작 하는 프로파일러에 알립니다.|  
|[RuntimeSuspendAborted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|런타임에 발생 하는 런타임 일시 중단 중단는 프로파일러에 알립니다.|  
|[RuntimeSuspendFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|런타임에 모든 런타임 스레드 일시 중단 완료 되었음을 프로파일러에 알립니다.|  
|[RuntimeSuspendStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|모든 런타임 스레드를 일시 중단 하려고 합니다. 런타임에서 프로파일러에 알립니다.|  
|[RuntimeThreadResumed 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|지정된 된 스레드의 일시 중단 된 후 다시 시작 했습니다는 프로파일러에 알립니다.|  
|[RuntimeThreadSuspended 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|지정된 된 스레드에 된 방식 또는, 곧 일시 중단 되는 프로파일러에 알립니다.|  
|[Shutdown 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|응용 프로그램이 종료 되는 프로파일러에 알립니다.|  
|[ThreadAssignedToOSThread 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|관리 되는 스레드를 특정 운영 체제 (OS) 스레드를 사용 하 여 구현 되 고 있음을 프로파일러에 알립니다.|  
|[ThreadCreated 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|스레드 생성 되어 있는지를 프로파일러에 알립니다.|  
|[ThreadDestroyed 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|스레드 소멸 된 프로파일러에 알립니다.|  
|[UnmanagedToManagedTransition 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|비관리 코드에서 관리 코드로 전환 되었음을 프로파일러에 알립니다.|  
  
## <a name="remarks"></a>설명  
 CLR에서 메서드를 호출 합니다 `ICorProfilerCallback` (또는 [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) 인터페이스는 프로파일러가 구독, 이벤트를 프로파일러에 알리기 위해 발생 합니다. CLR 코드 프로파일러를 사용 하 여 통신 하는 기본 콜백 인터페이스입니다.  
  
 코드 프로파일러가의 메서드를 구현 해야 합니다는 `ICorProfilerCallback` 인터페이스입니다. .NET Framework 버전 2.0 이상에서는 프로파일러도 구현 해야 합니다는 `ICorProfilerCallback2` 메서드. 각 메서드 구현은 실패 시 성공 시 s_ok이 고,의 값이 있는 HRESULT 또는 E_FAIL을 반환 해야 합니다. CLR에서 제외 하 고 각 콜백에 의해 반환 되는 HRESULT를 무시 하는 현재 [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)합니다.  
  
 코드 프로파일러가 Microsoft Windows 레지스트리를 구현 하는 해당 구성 요소 개체 모델 (COM) 개체에 등록 해야 합니다 `ICorProfilerCallback` 고 `ICorProfilerCallback2` 인터페이스입니다. 코드 프로파일러는 호출 하 여 알림을 수신 하려는 이벤트를 구독할 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)합니다. 프로파일러의 구현에서는 일반적으로 이렇게 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)합니다. 프로파일러는 이벤트 수행 되려고 하거나 실행 중인 런타임 프로세스에서 발생 한 직후 때 런타임에서 알림을 수신 합니다.  
  
> [!NOTE]
>  프로파일러는 단일 COM 개체를 등록합니다. 프로파일러를.NET Framework 버전 1.0 또는 1.1, COM 개체의 메서드만 구현 해야 하는 경우 대상 `ICorProfilerCallback`합니다. COM 개체의 메서드를 구현 해야.NET Framework 2.0 이상 버전을 대상으로 하는 경우 `ICorProfilerCallback2`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerCallback4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
