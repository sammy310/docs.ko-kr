---
title: IValidator::Validate 메서드
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 8ae47eac713fbee30ea543538957b12460b8e1fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123277"
---
# <a name="ivalidatorvalidate-method"></a>IValidator::Validate 메서드
지정 된 PE (이식 가능한 실행 파일) 또는 MSIL (Microsoft 중간 언어) 파일의 유효성을 검사 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `veh`  
 진행 유효성 검사 오류를 처리 하는 `IVEHandler` 인스턴스에 대 한 포인터입니다.  
  
 `pAppDomain`  
 진행 파일이 로드 되는 응용 프로그램 도메인에 대 한 포인터입니다.  
  
 `ulFlags`  
 진행 수행 해야 하는 유효성 검사를 나타내는 [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) 값의 비트 조합입니다.  
  
 `ulMaxError`  
 진행 유효성 검사를 종료 하기 전에 허용 되는 최대 오류 수입니다.  
  
 `token`  
 진행 사용 되지 않습니다.  
  
 `fileName`  
 진행 유효성을 검사할 파일의 이름을 지정 하는 문자열입니다.  
  
 `pe`  
 진행 파일이 저장 되는 메모리 버퍼에 대 한 포인터입니다.  
  
 `ulSize`  
 진행 유효성을 검사할 파일의 크기 (바이트)입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** IValidator, IValidator. h  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
