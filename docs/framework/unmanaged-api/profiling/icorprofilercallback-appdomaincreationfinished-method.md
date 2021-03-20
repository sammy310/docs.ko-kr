---
description: '자세히 알아보기: ICorProfilerCallback:: AppDomainCreationFinished 메서드'
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
ms.openlocfilehash: 51ed9ba19d96fd6ea05d05b07fe329aa9c01f290
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760758"
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

`appDomainId` 진행 만든 도메인을 식별 합니다.

`hrStatus` 진행 응용 프로그램 도메인 만들기가 성공적으로 완료 되었는지 여부를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명  

 메서드를 호출할 때까지 모든 정보 요청에 대해 응용 프로그램 ID가 유효 하지 않습니다 `AppDomainCreationFinished` .  
  
 응용 프로그램 도메인 로드의 일부 부분은 콜백 후에도 계속 `AppDomainCreationFinished` 됩니다. 의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다. 그러나의 성공 HRESULT는 `hrStatus` 응용 프로그램 도메인을 만드는 첫 번째 부분이 성공 했다는 것을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
