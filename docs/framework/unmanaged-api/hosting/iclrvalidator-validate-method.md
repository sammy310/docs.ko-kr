---
title: ICLRValidator::Validate 메서드
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: 18492f3e95947a3a11da9d5d303651c04d764a8f
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762632"
---
# <a name="iclrvalidatorvalidate-method"></a>ICLRValidator::Validate 메서드
지정 된 파일에서 PE (이식 가능한 실행) 또는 MSIL (Microsoft 중간 언어)의 유효성을 검사 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a>매개 변수  
 `veh`  
 진행 `IVEHandler`유효성 검사 오류를 처리 하는 인스턴스에 대 한 포인터입니다.  
  
 `ulAppDomainId`  
 진행 현재의 식별자입니다 <xref:System.AppDomain> .  
  
 `ulFlags`  
 진행 수행 해야 하는 유효성 검사의 종류를 나타내는 [ValidatorFlags](validatorflags-enumeration.md) 값의 조합입니다.  
  
 `ulMaxError`  
 진행 유효성 검사를 종료 하기 전에 허용 되는 최대 오류 수입니다.  
  
 `token`  
 진행 사용 되지 않는.  
  
 `fileName`  
 진행 유효성을 검사할 파일의 이름입니다.  
  
 `pe`  
 진행 파일 버퍼에 대 한 포인터입니다.  
  
 `ulSize`  
 진행 유효성을 검사할 파일의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`Validate`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** IValidator, IValidator. h  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRValidator 인터페이스](iclrvalidator-interface.md)
