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
ms.openlocfilehash: 8b3f7712436c001e5cd44f214f6edb06390abd41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177074"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>ICorProfilerCallback::AppDomainCreationFinished 메서드
프로파일러에 응용 프로그램 도메인이 생성되었음을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a>매개 변수

- `appDomainId`

  \[in] 생성된 도메인을 식별합니다.

- `hrStatus`

  \[in] 응용 프로그램 도메인 만들기가 성공적으로 완료되었는지 여부를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명  
 `AppDomainCreationFinished` 응용 프로그램 ID는 메서드가 호출될 때까지 정보 요청에 대해 유효하지 않습니다.  
  
 `AppDomainCreationFinished` 콜백 이후에 응용 프로그램 도메인로드의 일부가 계속될 수 있습니다. 오류 HRESULT `hrStatus` in은 오류를 나타냅니다. 그러나 HRESULT의 `hrStatus` 성공은 응용 프로그램 도메인을 만드는 첫 번째 부분이 성공했음을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
