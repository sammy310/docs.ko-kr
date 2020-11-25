---
title: ICLRValidator::FormatEventInfo 메서드
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
ms.openlocfilehash: a3f52deab4d0c8ca56fae2e65912217e51abe58a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715877"
---
# <a name="iclrvalidatorformateventinfo-method"></a>ICLRValidator::FormatEventInfo 메서드

지정 된 유효성 검사 오류에 대 한 자세한 메시지를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `hVECode`  
 진행 유효성 검사 오류 처리기에 전달 된 HRESULT 값입니다.  
  
 `Context`  
 진행 `VEContext` 유효성 검사 오류에 대 한 컨텍스트 정보를 포함 하는 인스턴스입니다.  
  
 `msg`  
 [in, out] 친숙 한 오류 메시지입니다.  
  
 `ulMaxLength`  
 진행 오류 메시지의 최대 길이입니다.  
  
 `psa`  
 진행 메시지에 사용할 안전한 추가 매개 변수 배열입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`FormatEventInfo` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** IValidator, IValidator. h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRErrorReportingManager 인터페이스](iclrerrorreportingmanager-interface.md)
- [ICLRValidator 인터페이스](iclrvalidator-interface.md)
