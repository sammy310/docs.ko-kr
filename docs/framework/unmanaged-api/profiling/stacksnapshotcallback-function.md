---
title: StackSnapshotCallback 함수
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
ms.openlocfilehash: c0cec9eb7bb8bbc94b255152a9b4d79108bdd1b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427071"
---
# <a name="stacksnapshotcallback-function"></a>StackSnapshotCallback 함수
[ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 메서드에서 시작 하는 스택 워크를 실행 하는 동안 스택에서 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 프로파일러에 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `funcId`  
 진행 이 값이 0 인 경우이 콜백은 관리 되지 않는 프레임의 실행에 대 한 것입니다. 그렇지 않은 경우 관리 되는 함수의 식별자 이며이 콜백은 관리 되는 프레임에 대 한 것입니다.  
  
 `ip`  
 진행 프레임에 있는 네이티브 코드 명령 포인터의 값입니다.  
  
 `frameInfo`  
 진행 스택 프레임에 대 한 정보를 참조 하는 `COR_PRF_FRAME_INFO` 값입니다. 이 값은이 콜백 하는 동안에만 유효 합니다.  
  
 `contextSize`  
 진행 `context` 매개 변수에서 참조 하는 `CONTEXT` 구조체의 크기입니다.  
  
 `context`  
 진행 이 프레임의 CPU 상태를 나타내는 Win32 `CONTEXT` 구조체에 대 한 포인터입니다.  
  
 `context` 매개 변수는 COR_PRF_SNAPSHOT_CONTEXT 플래그가 `ICorProfilerInfo2::DoStackSnapshot`전달 된 경우에만 유효 합니다.  
  
 `clientData`  
 진행 `ICorProfilerInfo2::DoStackSnapshot`에서 직접 전달 되는 클라이언트 데이터에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `StackSnapshotCallback` 함수는 프로파일러 작성기에 의해 구현 됩니다. `StackSnapshotCallback`에서 수행 되는 작업의 복잡성을 제한 해야 합니다. 예를 들어 비동기 방식으로 `ICorProfilerInfo2::DoStackSnapshot`를 사용 하는 경우 대상 스레드가 잠금을 보유 하 고 있을 수 있습니다. `StackSnapshotCallback` 내의 코드가 동일한 잠금을 필요로 하는 경우 교착 상태가 뒤따르게 수 있습니다.  
  
 `ICorProfilerInfo2::DoStackSnapshot` 메서드는 관리 되는 프레임 마다 한 번씩 또는 관리 되지 않는 프레임 실행 마다 한 번씩 `StackSnapshotCallback` 함수를 호출 합니다. 관리 되지 않는 프레임 실행에 대 한 `StackSnapshotCallback`를 호출 하는 경우 프로파일러는 `context` 매개 변수에서 참조 하는 register 컨텍스트를 사용 하 여 관리 되지 않는 자체 스택 워크를 수행할 수 있습니다. 이 경우 Win32 `CONTEXT` 구조는 관리 되지 않는 프레임 실행 내에서 가장 최근에 푸시되는 프레임의 CPU 상태를 나타냅니다. Win32 `CONTEXT` 구조에 모든 레지스터의 값이 포함 되어 있지만 스택 포인터 레지스터, 프레임 포인터 레지스터, 명령 포인터 레지스터 및 비휘발성 (즉, 유지 되는) 정수 레지스터의 값만 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [DoStackSnapshot 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [프로파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
