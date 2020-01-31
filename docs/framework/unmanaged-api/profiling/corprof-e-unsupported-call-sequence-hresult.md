---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
ms.openlocfilehash: b4ab5c8f7cdca1303cb4fbbc4fa39db3c5977c15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867011"
---
# <a name="corprof_e_unsupported_call_sequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT

CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT는 .NET Framework 버전 2.0에서 도입 되었습니다. .NET Framework 4는 다음과 같은 두 가지 시나리오에서이 HRESULT를 반환 합니다.  
  
- 하이재킹 프로파일러가 스레드의 레지스터 컨텍스트를 임의 시간에 강제로 다시 설정 하 여 스레드가 일관 되지 않은 상태에 있는 구조에 액세스 하려고 시도 하는 경우  
  
- 프로파일러가 가비지 수집을 금지 하는 콜백 메서드에서 가비지 수집을 트리거하는 정보 메서드를 호출 하려고 하는 경우  
  
다음 섹션에서는 이러한 두 가지 시나리오에 대해 설명 합니다.  
  
## <a name="hijacking-profilers"></a>하이재킹 프로파일러  

  이 시나리오는 하이재킹 프로파일러가이 HRESULT를 볼 수 있는 경우도 있지만 하이재킹 프로파일러와 관련 된 문제입니다.  
  
 이 시나리오에서 하이재킹 프로파일러는 스레드가 프로파일러 코드를 입력 하거나 [ICorProfilerInfo](icorprofilerinfo-interface.md) 메서드를 통해 CLR (공용 언어 런타임)을 다시 입력할 수 있도록 스레드의 레지스터 컨텍스트를 임의 시간에 강제로 다시 설정 합니다.  
  
 프로 파일링 API가 제공 하는 많은 Id는 CLR의 데이터 구조를 가리킵니다. 많은 `ICorProfilerInfo` 호출은 단순히 이러한 데이터 구조의 정보를 읽고 다시 전달 합니다. 그러나 CLR은 실행 될 때 해당 구조에서 항목을 변경할 수 있으며 잠금을 사용 하 여이 작업을 수행할 수 있습니다. 프로파일러가 스레드를 도용 했을 때 CLR이 이미 잠금을 보유 하 고 있거나 획득 하려고 한다고 가정 합니다. 스레드가 CLR을 후 하 고 수정 중인 프로세스에서 더 많은 잠금을 시도 하거나 구조를 검사 하려고 하면 이러한 구조가 일관 되지 않은 상태일 수 있습니다. 교착 상태 및 액세스 위반은 이러한 상황에서 쉽게 발생할 수 있습니다.  
  
 일반적으로 하이재킹이 아닌 프로파일러가 [ICorProfilerCallback](icorprofilercallback-interface.md) 메서드 내에서 코드를 실행 하 고 유효한 매개 변수를 사용 하 여 `ICorProfilerInfo` 메서드로 호출 하는 경우 교착 상태가 되거나 액세스 위반을 받지 않아야 합니다. 예를 들어, [ICorProfilerCallback:: ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) 메서드 내에서 실행 되는 프로파일러 코드는 [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) 메서드를 호출 하 여 클래스에 대 한 정보를 요청할 수 있습니다. 코드는 정보를 사용할 수 없음을 나타내는 CORPROF_E_DATAINCOMPLETE HRESULT를 받을 수 있습니다. 그러나 교착 상태 또는 액세스 위반을 받지 않습니다. 이러한 `ICorProfilerInfo` 호출은 `ICorProfilerCallback` 메서드에서 이루어지기 때문에 동기로 간주 됩니다.  
  
 그러나 `ICorProfilerCallback` 메서드 내에 없는 코드를 실행 하는 관리 되는 스레드는 비동기 호출을 수행 하는 것으로 간주 됩니다. .NET Framework 버전 1에서는 비동기 호출에서 발생할 수 있는 작업을 확인 하기 어렵습니다. 호출이 교착 상태 또는 충돌을 발생 하거나 잘못 된 대답을 제공할 수 있습니다. .NET Framework 버전 2.0에는이 문제를 방지 하는 데 도움이 되는 몇 가지 간단한 검사가 도입 되었습니다. .NET Framework 2.0에서는 안전 하지 않은 `ICorProfilerInfo` 함수를 비동기적으로 호출 하는 경우 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT를 사용 하 여 실패 합니다.  
  
 일반적으로 비동기 호출은 안전 하지 않습니다. 그러나 다음 메서드는 안전 하며 특히 비동기 호출을 지원 합니다.  
  
- [GetEventMask](icorprofilerinfo-geteventmask-method.md)  
  
- [SetEventMask](icorprofilerinfo-seteventmask-method.md)  
  
- [GetCurrentThreadID](icorprofilerinfo-getcurrentthreadid-method.md)  
  
- [GetThreadContext](icorprofilerinfo-getthreadcontext-method.md)  
  
- [GetThreadAppDomain](icorprofilerinfo2-getthreadappdomain-method.md)  
  
- [GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md)  
  
- [GetFunctionInfo](icorprofilerinfo-getfunctioninfo-method.md)  
  
- [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- [GetCodeInfo](icorprofilerinfo-getcodeinfo-method.md)  
  
- [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)  
  
- [GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md)  
  
- [GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md)  
  
- [GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)  
  
- [IsArrayClass](icorprofilerinfo-isarrayclass-method.md)  
  
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)  
  
- [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)  
  
 자세한 내용은 CLR 프로 파일링 API 블로그에서 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE 된 이유](https://docs.microsoft.com/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) 항목을 참조 하세요.  
  
## <a name="triggering-garbage-collections"></a>가비지 컬렉션 트리거  
 이 시나리오는 가비지 수집을 금지 하는 콜백 메서드 (예: `ICorProfilerCallback` 메서드 중 하나) 내에서 실행 되는 프로파일러를 포함 합니다. 프로파일러가 가비지 수집을 트리거할 수 있는 정보 메서드 (예: `ICorProfilerInfo` 인터페이스의 메서드)를 호출 하려고 시도 하는 경우 정보 메서드는 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT를 사용 하 여 실패 합니다.  
  
 다음 표에서는 가비지 수집을 금지 하는 콜백 메서드와 가비지 수집을 트리거할 수 있는 정보 메서드를 보여 줍니다. 프로파일러가 나열 된 콜백 메서드 중 하나를 실행 하 고 나열 된 정보 메서드 중 하나를 호출 하는 경우 해당 정보 메서드는 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT를 사용 하 여 실패 합니다.  
  
|가비지 수집을 금지 하는 콜백 메서드|가비지 수집을 트리거하는 정보 메서드|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 인터페이스](icorprofilercallback2-interface.md)
- [ICorProfilerCallback3 인터페이스](icorprofilercallback3-interface.md)
- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](icorprofilerinfo2-interface.md)
- [ICorProfilerInfo3 인터페이스](icorprofilerinfo3-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
