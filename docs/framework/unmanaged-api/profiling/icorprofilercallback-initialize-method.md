---
description: '자세히 알아보기: ICorProfilerCallback:: Initialize 메서드'
title: ICorProfilerCallback::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: b3ff579dee384b331450aa54aace39890febfe30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705943"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize 메서드

새 CLR (공용 언어 런타임) 응용 프로그램이 시작 될 때마다 코드 프로파일러를 초기화 하기 위해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>매개 변수

- `pICorProfilerInfoUnk`

  \[in] 프로파일러가 [ICorProfilerInfo](icorprofilerinfo-interface.md) 인터페이스 포인터를 쿼리해야 하는 [IUnknown](/cpp/atl/iunknown) 인터페이스에 대 한 포인터입니다.  

## <a name="remarks"></a>설명  

 `Initialize`이 호출은 변경할 수 없는 콜백을 활성화 (또는 비활성화) 하는 유일한 기회입니다. 호출로 콜백을 사용 하도록 설정한 후 `Initialize` 에는 나중에 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)를 사용 하 여 콜백을 사용 하지 않도록 설정할 수 없습니다. [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형의 COR_PRF_MONITOR_IMMUTABLE 값은 변경할 수 없는 이벤트를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [Shutdown 메서드](icorprofilercallback-shutdown-method.md)
