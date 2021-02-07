---
description: '자세히 알아보기: StackSnapshotCallback 함수'
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
ms.openlocfilehash: a49588bc3277956acad612afd0fcab3fa7edffbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736858"
---
# <a name="stacksnapshotcallback-function"></a>StackSnapshotCallback 함수

[ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드에서 시작 하는 스택 워크를 실행 하는 동안 스택에서 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보를 프로파일러에 제공 합니다.  
  
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
 진행 `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 참조 하는 값입니다. 이 값은이 콜백 하는 동안에만 유효 합니다.  
  
 `contextSize`  
 진행 `CONTEXT` 매개 변수에서 참조 하는 구조체의 크기입니다 `context` .  
  
 `context`  
 진행 `CONTEXT` 이 프레임의 CPU 상태를 나타내는 Win32 구조체에 대 한 포인터입니다.  
  
 `context`매개 변수는 COR_PRF_SNAPSHOT_CONTEXT 플래그가 전달 된 경우에만 유효 `ICorProfilerInfo2::DoStackSnapshot` 합니다.  
  
 `clientData`  
 진행 에서 직접 전달 되는 클라이언트 데이터에 대 한 포인터입니다 `ICorProfilerInfo2::DoStackSnapshot` .  
  
## <a name="remarks"></a>설명  

 `StackSnapshotCallback`함수는 프로파일러 작성기에 의해 구현 됩니다. 에서 수행 되는 작업의 복잡성을 제한 해야 합니다 `StackSnapshotCallback` . 예를 들어 비동기 방식으로를 사용 하 `ICorProfilerInfo2::DoStackSnapshot` 는 경우 대상 스레드가 잠금을 보유 하 고 있을 수 있습니다. 내의 코드에 `StackSnapshotCallback` 동일한 잠금이 필요한 경우 교착 상태가 뒤따르게 수 있습니다.  
  
 `ICorProfilerInfo2::DoStackSnapshot`메서드는 `StackSnapshotCallback` 관리 되는 프레임당 한 번 또는 관리 되지 않는 프레임의 실행 당 한 번씩 함수를 호출 합니다. `StackSnapshotCallback`관리 되지 않는 프레임의 실행에 대해를 호출 하면 프로파일러에서 등록 컨텍스트 (매개 변수로 참조 됨)를 사용 `context` 하 여 관리 되지 않는 자체 스택 워크를 수행할 수 있습니다. 이 경우 Win32 `CONTEXT` 구조는 관리 되지 않는 프레임 실행 내에서 가장 최근에 푸시되는 프레임의 CPU 상태를 나타냅니다. Win32 구조에 `CONTEXT` 모든 레지스터의 값이 포함 되어 있지만 스택 포인터 레지스터, 프레임 포인터 레지스터, 명령 포인터 레지스터 및 비휘발성 (즉, 유지 되는) 정수 레지스터의 값만 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [DoStackSnapshot 메서드](icorprofilerinfo2-dostacksnapshot-method.md)
- [프로파일링 전역 정적 함수](profiling-global-static-functions.md)
