---
title: NextMethod 함수(관리되지 않는 API 참조)
description: NextMethod 함수는 열거형에서 다음 메서드를 검색합니다.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174929"
---
# <a name="nextmethod-function"></a>NextMethod 함수
[BeginMethod Enumeration에](beginmethodenumeration.md)대 한 호출로 시작 하는 열거형에서 다음 메서드를 검색합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`lFlags`  
[in] 예약되어 있습니다. 이 매개변수는 0이어야 합니다.

`pName`  
【아웃】 호출 하기 전에 `null` 가리키는 포인터입니다. 함수가 반환되면 메서드 이름이 `BSTR` 포함된 새 주소입니다.

`ppSignatureIn`  
【아웃】 메서드에 대 한 매개 변수를 포함 하는 [IWbemClassObject에](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 대 한 포인터를 `in` 받는 포인터입니다.

`ppSignatureOut`  
【아웃】 메서드에 대 한 매개 변수를 포함 하는 [IWbemClassObject에](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 대 한 포인터를 `out` 받는 포인터입니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | 함수에 대한 호출이 [`BeginEnumeration`](beginenumeration.md) 없습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 열거형에는 더 이상 속성이 없습니다. |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 메서드에 대한 호출을 래핑합니다.

호출자는 [BeginMethodEnumeration](beginmethodenumeration.md) 함수를 호출하여 열거 시퀀스를 시작한 다음 함수가 반환될 `WBEM_S_NO_MORE_DATA`때까지 [NextMethod] 함수를 호출합니다. 선택적으로 호출자는 [EndMethodEnumeration을](endmethodenumeration.md)호출하여 시퀀스를 완료합니다. 호출자는 언제든지 [EndMethodEnmeration을](endmethodenumeration.md) 호출하여 열거를 조기에 종료할 수 있습니다.

## <a name="example"></a>예제

C++ 예제는 [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 메서드를 참조하십시오.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
