---
title: GetMethodOrigin 함수(관리되지 않는 API 참조)
description: GetMethodOrigin 함수는 메서드가 선언되는 클래스를 결정합니다.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5b4609b6649be875aea7dfcf52ba36b1e98ab7bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176801"
---
# <a name="getmethodorigin-function"></a>GetMethodOrigin 함수
메서드가 선언되는 클래스를 결정합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`wszMethodName`  
【인】 소유 클래스가 요청되는 개체에 대한 메서드의 이름입니다.

`pstrClassName`  
【아웃】 메서드를 소유 하는 클래스의 이름을 받습니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 메서드를 찾을 수 없습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 잘못되었습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) 메서드에 대한 호출을 래핑합니다.

클래스는 하나 이상의 기본 클래스에서 메서드를 상속할 수 있으므로 개발자는 지정된 메서드가 정의된 클래스를 결정하려고 하는 경우가 많습니다.

이 `pstrClassName` 매개 변수는 매개 `BSTR` 변수이기 때문에 함수가 `out` 호출되기 전에 유효한 매개 변수를 가리키지 않아야 합니다. 이 포인터는 함수가 반환된 후 할당 되지 않습니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
