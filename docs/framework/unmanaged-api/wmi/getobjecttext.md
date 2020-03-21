---
title: GetObjectText 함수(관리되지 않는 API 참조)
description: GetObjectText 함수는 MOF 구문에서 개체의 텍스트 렌더링을 반환합니다.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176788"
---
# <a name="getobjecttext-function"></a>GetObjectText 함수
MOF(관리되는 개체 형식) 구문에서 개체의 텍스트 렌더링을 반환합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`lFlags`  
【인】 일반적으로 0. (또는 0x1)를 지정하면 `WBEM_FLAG_NO_FLAVORS` 한정자가 전파 또는 풍미 정보 없이 포함됩니다.

`pstrObjectText`【아웃】 `null` 항목에 대한 포인터입니다. 반환시 개체의 MOF 구문 렌더링을 포함 하는 새로 할당 된 `BSTR` 개체입니다.  

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반적인 오류가 발생했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못된 경우 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) 메서드에 대한 호출을 래핑합니다.

반환된 MOF 텍스트에는 개체에 대한 모든 정보가 포함되지 않지만 MOF 컴파일러가 원래 개체를 다시 만들 수 있는 충분한 정보만 포함됩니다. 예를 들어 전파된 한정자 또는 상위 클래스 속성은 포함되지 않습니다.

다음 알고리즘은 메서드의 매개 변수의 텍스트를 재구성하는 데 사용됩니다.

1. 매개 변수는 식별자 값의 순서로 순서가 다시 정렬됩니다.
1. 단일 매개 변수로 `[in]` `[out]` 지정되고 결합된 매개 변수입니다.

`pstrObjectText`함수가 호출될 `null` 때의 포인터여야 합니다. 포인터가 할당 할당되지 않으므로 메서드 호출 전에 유효한 문자열을 가리키지 않아야 합니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
