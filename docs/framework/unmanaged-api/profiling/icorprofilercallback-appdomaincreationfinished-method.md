---
title: ICorProfilerCallback::AppDomainCreationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: 1cf3f2b62b388b6c2d6fcd75b1b07a67d5b2e49f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866705"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>ICorProfilerCallback::AppDomainCreationFinished 메서드
응용 프로그램 도메인이 생성 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a>매개 변수

- `appDomainId`

  \[in]은 생성 된 도메인을 식별 합니다.

- `hrStatus`

  \[] 응용 프로그램 도메인 만들기가 성공적으로 완료 되었는지 여부를 나타내는 HRESULT입니다.

## <a name="remarks"></a>주의  
 `AppDomainCreationFinished` 메서드를 호출할 때까지 모든 정보 요청에 대해 응용 프로그램 ID가 유효 하지 않습니다.  
  
 응용 프로그램 도메인 로드의 일부 부분은 `AppDomainCreationFinished` 콜백 후에도 계속 될 수 있습니다. `hrStatus` 오류 HRESULT는 오류를 나타냅니다. 그러나 `hrStatus`의 성공 HRESULT는 응용 프로그램 도메인을 만드는 첫 번째 부분이 성공 했다는 것만 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
