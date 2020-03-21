---
title: WritePropertyValue 함수(관리되지 않는 API 참조)
description: WritePropertyValue 함수는 속성에 바이트를 씁니다.
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
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174838"
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
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) 인스턴스에 대한 포인터입니다.

`lHandle`  
【인】 이 속성을 식별하는 핸들을 포함하는 정수입니다. [GetPropertyHandle](getpropertyhandle.md) 함수를 호출하여 핸들을 검색할 수 있습니다.

`lNumBytes`  
【인】 속성에 기록되는 바이트 수입니다. 자세한 내용은 [비고](#remarks) 섹션을 참조하십시오.

`pHandle`【아웃】 데이터를 포함하는 바이트 배열에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못된 경우 |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | 형식이 맞지 않는 경우 |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) 메서드에 대 한 호출을 래핑합니다.

이 함수를 사용하여 문자열 및`DWORD` 기타 모든`QWORD` 비데이터 또는 비데이터를 설정합니다.

비string 속성 값의 경우 지정된 속성 형식의 올바른 데이터 `lNumBytes` 크기여야 합니다. string 속성 값의 `lNumBytes` 경우 지정된 문자열의 길이바이트여야 하며 문자열 자체는 바이트의 짝수 길이여야 하며 null-termination 문자가 따라야 합니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
