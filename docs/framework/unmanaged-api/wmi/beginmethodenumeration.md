---
title: BeginMethodEnumeration 함수(관리되지 않는 API 참조)
description: BeginMethodEnumeration 함수는 개체의 메서드 열거를 시작합니다.
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 876f5810fffab7fa98cd4d46715e13569ab95f6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175046"
---
# <a name="beginmethodenumeration-function"></a>BeginMethodEnumeration 함수
개체에 사용할 수 있는 메서드의 열거를 시작합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문  
  
```cpp
HRESULT BeginMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`lEnumFlags`  
【인】 모든 메서드에 대해 0(0) 또는 열거형 범위를 지정하는 플래그입니다. 다음 플래그는 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

지속적임  |값  |Description  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 열거형은 클래스 자체에 정의된 메서드로 제한합니다. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 열거형은 기본 클래스에서 상속되는 속성으로 제한합니다. |

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lEnnumFlags`0이 아니며 지정된 플래그 중 하나가 아닙니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) 메서드에 대한 호출을 래핑합니다.

이 메서드 호출은 현재 개체가 클래스 정의인 경우에만 지원됩니다. 메서드 조작은 인스턴스를 가리키는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포인터에서 사용할 수 없습니다. 메서드가 누거되는 순서는 [지정된 IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)의 지정된 인스턴스에 대해 고정되어 있음을 보장합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
