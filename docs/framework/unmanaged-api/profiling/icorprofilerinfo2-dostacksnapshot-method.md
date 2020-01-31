---
title: ICorProfilerInfo2::DoStackSnapshot 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
ms.openlocfilehash: 49b1769ade8e8b71c146a818523b124984c44ed6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868892"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot 메서드
스택에서 관리 되는 프레임을 지정 된 스레드에 대해 보여 주고 콜백을 통해 프로파일러에 정보를 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a>매개 변수  
 `thread`  
 진행 대상 스레드의 ID입니다.  
  
 `thread`에서 null을 전달 하면 현재 스레드의 스냅숏이 생성 됩니다. 다른 스레드의 `ThreadID` 전달 되 면 CLR (공용 언어 런타임)은 해당 스레드를 일시 중단 하 고, 스냅숏을 수행 하 고,를 다시 시작 합니다.  
  
 `callback`  
 진행 [StackSnapshotCallback](stacksnapshotcallback-function.md) 메서드의 구현에 대 한 포인터로, 프로파일러에 관리 되는 각 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 제공 하기 위해 CLR에서 호출 됩니다.  
  
 `StackSnapshotCallback` 메서드는 프로파일러 작성기에 의해 구현 됩니다.  
  
 `infoFlags`  
 진행 `StackSnapshotCallback`하 여 각 프레임에 대해 다시 전달할 데이터 양을 지정 하는 [COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md) 열거형의 값입니다.  
  
 `clientData`  
 진행 `StackSnapshotCallback` 콜백 함수로 직접 전달 되는 클라이언트 데이터에 대 한 포인터입니다.  
  
 `context`  
 진행 스택 워크의 초기값으로 사용 되는 Win32 `CONTEXT` 구조체에 대 한 포인터입니다. Win32 `CONTEXT` 구조는 CPU 레지스터의 값을 포함 하며 특정 시점의 CPU 상태를 나타냅니다.  
  
 초기값을 사용 하면 스택의 위쪽이 관리 되지 않는 도우미 코드 이면 CLR에서 스택 워크를 시작할 위치를 결정할 수 있습니다. 그렇지 않으면 초기값은 무시 됩니다. 비동기 워크에 대해 초기값을 제공 해야 합니다. 동기식 연습을 수행 하는 경우 시드가 필요 하지 않습니다.  
  
 `context` 매개 변수는 COR_PRF_SNAPSHOT_CONTEXT 플래그가 `infoFlags` 매개 변수에 전달 된 경우에만 유효 합니다.  
  
 `contextSize`  
 진행 `context` 매개 변수에서 참조 하는 `CONTEXT` 구조체의 크기입니다.  
  
## <a name="remarks"></a>주의  
 `thread` null을 전달 하면 현재 스레드의 스냅숏이 생성 됩니다. 대상 스레드가 현재 일시 중단 된 경우에만 다른 스레드에 대 한 스냅숏을 만들 수 있습니다.  
  
 프로파일러가 스택을 탐색 하려는 경우 `DoStackSnapshot`를 호출 합니다. CLR이 해당 호출에서 반환 되기 전에 스택에서 각 관리 되는 프레임 (또는 관리 되지 않는 프레임의 실행)에 대해 한 번씩 여러 번 `StackSnapshotCallback`를 호출 합니다. 관리 되지 않는 프레임이 발견 되 면 직접 탐색 해야 합니다.  
  
 스택이 푸시되는 순서는 프레임을 스택에 푸시하는 방법입니다. 리프 (마지막 푸시) 프레임 먼저, 주 (첫 번째 푸시) 프레임이 마지막입니다.  
  
 관리 되는 스택을 탐색 하기 위해 프로파일러를 프로그래밍 하는 방법에 대 한 자세한 내용은 [.NET Framework 2.0: 기본 사항 및 그 이상에서 프로파일러 스택 탐색](https://docs.microsoft.com/previous-versions/dotnet/articles/bb264782(v=msdn.10))을 참조 하세요.  
  
 다음 섹션에서 설명 하는 것 처럼 스택 워크는 동기식 또는 비동기식 일 수 있습니다.  
  
## <a name="synchronous-stack-walk"></a>동기 스택 워크  
 동기 스택 워크에는 콜백에 대 한 응답으로 현재 스레드의 스택을 탐색 하는 작업이 포함 됩니다. 시드 또는 일시 중단은 필요 하지 않습니다.  
  
 프로파일러에서 [ICorProfilerCallback](icorprofilercallback-interface.md) (또는 [ICorProfilerCallback2](icorprofilercallback2-interface.md)) 메서드 중 하나를 호출 하는 CLR에 대 한 응답으로, 현재 스레드의 스택을 탐색 하기 위해 `DoStackSnapshot`를 호출 하는 경우 동기식 호출을 수행 합니다. 이는 [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md)된 것과 같은 알림에서 스택이 어떻게 표시 되는지 확인 하려는 경우에 유용 합니다. `ICorProfilerCallback` 메서드 내에서 `DoStackSnapshot`를 호출 하 여 `context` 및 `thread` 매개 변수에 null을 전달 하기만 하면 됩니다.  
  
## <a name="asynchronous-stack-walk"></a>비동기 스택 워크  
 비동기 스택 워크는 다른 스레드의 스택을 탐색 하거나 콜백에 대 한 응답으로는 아니지만 현재 스레드의 명령 포인터를 하이재킹 하 여 현재 스레드의 스택을 탐색 합니다. 스택의 맨 위에는 플랫폼 호출 (PInvoke) 또는 COM 호출의 일부가 아니지만 CLR 자체의 도우미 코드는 관리 되지 않는 코드를 사용 하는 경우 비동기 워크에 시드가 필요 합니다. 예를 들어 JIT (just-in-time) 컴파일 또는 가비지 수집을 수행 하는 코드는 도우미 코드입니다.  
  
 관리 되는 최상위 프레임을 찾을 때까지 대상 스레드를 직접 일시 중단 하 고 해당 스택을 직접 탐색 하 여 초기값을 얻을 수 있습니다. 대상 스레드를 일시 중단 한 후 대상 스레드의 현재 등록 컨텍스트를 가져옵니다. 그런 다음 [ICorProfilerInfo:: GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md) 를 호출 하 여 등록 컨텍스트가 비관리 코드를 가리키는지 여부를 확인 합니다. 0과 같은 `FunctionID` 반환 하는 경우 프레임은 비관리 코드입니다. 이제 첫 번째 관리 되는 프레임에 도달할 때까지 스택을 탐색 한 다음 해당 프레임에 대 한 등록 컨텍스트를 기준으로 초기값 컨텍스트를 계산 합니다.  
  
 시드 컨텍스트를 사용 하 여 `DoStackSnapshot`를 호출 하 여 비동기 스택 워크를 시작 합니다. 초기값을 제공 하지 않으면 스택의 맨 위에 있는 관리 되는 프레임을 건너뛸 수 `DoStackSnapshot`, 결과적으로 완료 되지 않은 스택 워크가 제공 됩니다. 초기값을 제공 하는 경우 JIT로 컴파일된 또는 네이티브 이미지 생성기 (Ngen.exe)에서 생성 된 코드를 가리켜야 합니다. 그렇지 않으면 `DoStackSnapshot` 오류 코드 CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX 반환 됩니다.  
  
 비동기 스택 워크는 이러한 지침을 따르지 않는 한 교착 상태 또는 액세스 위반을 쉽게 일으킬 수 있습니다.  
  
- 스레드를 직접 일시 중단 하는 경우 관리 코드를 실행 하지 않는 스레드만 다른 스레드를 일시 중단할 수 있습니다.  
  
- 스레드의 스택 워크가 완료 될 때까지 [ICorProfilerCallback:: ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md) 된 콜백이 항상 차단 됩니다.  
  
- 프로파일러가 가비지 수집을 트리거할 수 있는 CLR 함수를 호출 하는 동안에는 잠금을 보유 하지 않습니다. 즉, 소유 하는 스레드에서 가비지 수집을 트리거하는 호출을 수행할 수 있는 경우 잠금을 보유 하지 않습니다.  
  
 프로파일러에서 만든 스레드에서 `DoStackSnapshot`를 호출 하 여 별도의 대상 스레드의 스택을 탐색할 수 있는 경우 교착 상태가 발생할 수도 있습니다. 만든 스레드가 `DoStackSnapshot`를 포함 하 여 특정 `ICorProfilerInfo*` 메서드를 처음으로 입력 하면 CLR은 해당 스레드에서 스레드별, CLR 관련 초기화를 수행 합니다. 프로파일러가 실행 하려는 스택 대상 스레드를 일시 중단 하 고 해당 대상 스레드가이 스레드 단위 초기화를 수행 하는 데 필요한 잠금을 소유 하 고 있는 경우 교착 상태가 발생 합니다. 이 교착 상태를 방지 하려면 프로파일러에서 만든 스레드에서 `DoStackSnapshot`를 초기 호출 하 여 별도의 대상 스레드를 탐색 하 고 대상 스레드를 먼저 일시 중단 하지 않도록 합니다. 이 초기 호출을 통해 스레드 단위 초기화가 교착 상태 없이 완료 될 수 있도록 합니다. `DoStackSnapshot` 성공 하 고 하나 이상의 프레임을 보고 하는 경우 해당 시점 이후에 프로파일러에서 만든 스레드가 대상 스레드를 일시 중단 하 고 `DoStackSnapshot`를 호출 하 여 대상 스레드의 스택을 탐색 하는 것이 안전 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](icorprofilerinfo2-interface.md)
