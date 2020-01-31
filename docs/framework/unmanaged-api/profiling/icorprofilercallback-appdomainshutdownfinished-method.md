---
title: ICorProfilerCallback::AppDomainShutdownFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
ms.openlocfilehash: 0851ac33a2bac4fcf727cf09e5225f6b83481b50
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866678"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a>ICorProfilerCallback::AppDomainShutdownFinished 메서드
응용 프로그램 도메인이 프로세스에서 언로드 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>매개 변수

- `appDomainId`

  \[in] 응용 프로그램의 어셈블리가 저장 된 도메인을 식별 합니다.

- `hrStatus`

  \[in] 응용 프로그램 도메인이 언로드 되었는지 여부를 나타내는 HRESULT입니다.

## <a name="remarks"></a>주의  
 [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) 메서드가 반환 된 후에는 `appDomainId` 값이 정보 요청에 적합 하지 않습니다.  
  
 응용 프로그램 도메인 언로드의 일부 부분은 `AppDomainCreationFinished` 콜백 후에도 계속 될 수 있습니다. `hrStatus` 오류 HRESULT는 오류를 나타냅니다. 그러나 `hrStatus`의 성공 HRESULT는 응용 프로그램 도메인 언로드의 첫 번째 부분만 성공 했다는 것을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
