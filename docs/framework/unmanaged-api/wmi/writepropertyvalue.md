---
title: WritePropertyValue 함수 (관리 되지 않는 API 참조)
description: WritePropertyValue 함수 속성에 바이트를 씁니다.
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47120ff9de9e6e4802c5aea990841b235cd6c74c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783063"
---
# <a name="writepropertyvalue-function"></a>WritePropertyValue 함수
지정된 수의 바이트를 속성 핸들로 식별되는 속성에 씁니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) 인스턴스.

`lHandle`  
[in] 이 속성을 식별 하는 핸들을 포함 하는 정수입니다. 핸들을 호출 하 여 검색할 수는 [GetPropertyHandle](getpropertyhandle.md) 함수입니다.   

`lNumBytes`  
[in] 속성에 쓸 바이트 수입니다. 참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.

`pHandle`   
[out] 데이터를 포함 하는 바이트 배열에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못 되었습니다. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | 형식 불일치가 발생 했습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) 메서드.

이 함수를 사용 하 여 문자열 및 모든 다른 비-설정할`DWORD` 또는 비-`QWORD` 데이터입니다.

문자열이 아닌 속성 값에 대 한 `lNumBytes` 지정 된 속성 형식의 올바른 데이터 크기 여야 합니다. 문자열 속성 값에 대 한 `lNumBytes` 길이 여야 합니다 (바이트) 지정된 된 문자열 및 문자열을도 길이 (바이트) 이어야 합니다 자체 및이 null 종결 문자를 사용 하 여 따라야 합니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
