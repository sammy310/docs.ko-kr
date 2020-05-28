---
title: ValidatorFlags 열거형
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
ms.openlocfilehash: d5eb225241f597baf7a0a5584f4aaf8bf8411ea2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009472"
---
# <a name="validatorflags-enumeration"></a>ValidatorFlags 열거형
[ICLRValidator:: Validate](iclrvalidator-validate-method.md) 메서드에 대 한 호출에서 수행 해야 하는 유효성 검사의 형식을 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|실행 파일의 MSIL (Microsoft 중간 언어)만 유효성을 검사 하도록 지정 합니다.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|실행 파일의 형식만 유효성을 검사 하도록 지정 합니다.|  
|`VALIDATOR_EXTRA_VERBOSE`|모든 유효성 검사 유형을 수행 하 고 보고 하도록 지정 합니다.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|실행 파일의 형식에 대 한 유효성을 검사 하지 않도록 지정 합니다.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|유효성 검사 오류 메시지에 유효성 검사 오류를 발생 시키는 소스 코드 줄을 포함 하도록 지정 합니다. .NET Framework 버전 2.0에서는이 필드 값이 유효 하지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** IValidator, IValidator. h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRErrorReportingManager 인터페이스](iclrerrorreportingmanager-interface.md)
- [호스팅 열거형](hosting-enumerations.md)
