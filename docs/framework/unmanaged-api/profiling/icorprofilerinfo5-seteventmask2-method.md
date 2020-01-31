---
title: ICorProfilerInfo5::SetEventMask2 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 10e84b729c8af607165009a8591a69dbc1afcb1e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868384"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a>ICorProfilerInfo5::SetEventMask2 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 프로파일러가 CLR(공용 언어 런타임)에서 이벤트 알림을 받을 이벤트 형식을 지정하는 값을 설정합니다. [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드보다 더 많은 기능을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwEventsLow`  
 [in] 이벤트 범주를 지정하는 4바이트 값입니다. 각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다. 비트는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 설명 되어 있습니다.  
  
 `dwEventsHigh`  
 [in] 이벤트 범주를 지정하는 4바이트 값입니다.  각 비트는 서로 다른 기능, 동작 또는 이벤트 형식을 제어합니다. 비트는 [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) 열거형에 설명 되어 있습니다.  
  
## <a name="remarks"></a>주의  
 `SetEventMask2` 메서드를 사용하여 프로파일러가 구독하는 콜백을 설정합니다. 일반적으로 [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) 메서드를 호출 하 여 설정 되는 비트를 확인 하 고, 해당 `pdwEventsLow` 논리 OR을 수행한 다음 설정 하려는 새 비트를 `pdwEventsHigh` 하 고 `SetEventMask2` 메서드를 호출 합니다.  
  
 이 메서드는 [Seteventmask](icorprofilerinfo-seteventmask-method.md) 메서드 대신 권장 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo5 인터페이스](icorprofilerinfo5-interface.md)
- [GetEventMask2 메서드](icorprofilerinfo5-geteventmask2-method.md)
