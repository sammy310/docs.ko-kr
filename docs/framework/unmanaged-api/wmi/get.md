---
title: 함수 받기(관리되지 않는 API 참조)
description: Get 함수는 지정된 속성 값을 검색합니다.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 67fcfb301eebfcf4ed4fdcaa5c9ddf85c47a6073
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174981"
---
# <a name="get-function"></a>Get 함수

지정된 속성 값이 있는 경우 검색합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT Get (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a>매개 변수

`vFunc`\
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`\
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`wszName`\
【인】 속성의 이름입니다.

`lFlags`\
[in] 예약되어 있습니다. 이 매개변수는 0이어야 합니다.

`pVal`\
【아웃】 함수가 성공적으로 반환되면 `wszName` 속성 값이 포함됩니다. 인수는 `pval` 한정자에 대한 올바른 형식과 값을 할당합니다.

`pvtType`\
【아웃】 함수가 성공적으로 반환되면 속성 형식을 나타내는 [CIM 형식 상수가](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) 포함됩니다. 그 값은 `null`또한 될 수 있습니다.

`plFlavor`\
【아웃】 함수가 성공적으로 반환되면 속성의 원본에 대한 정보를 수신합니다. 해당 값은 `null` *WbemCli.h* 헤더 파일에 정의된 다음 WBEM_FLAVOR_TYPE 상수 중 하나일 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | 이 속성은 표준 시스템 속성입니다. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | 클래스의 경우: 속성은 부모 클래스에서 상속됩니다. <br> 인스턴스: 부모 클래스에서 상속된 속성은 인스턴스에서 수정되지 않았습니다.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | 클래스의 경우: 속성은 파생 클래스에 속합니다. <br> 인스턴스: 속성은 인스턴스에 의해 수정됩니다. 즉, 값이 제공되었지만 한정자가 추가또는 수정되었습니다. |

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반적인 오류가 발생했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 잘못되었습니다. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 속성을 찾을 수 없습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |

## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject:Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) 메서드에 대한 호출을 래핑합니다.

이 `Get` 함수는 시스템 속성을 반환할 수도 있습니다.

`pVal`인수에는 한정자와 COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) 함수에 대 한 올바른 형식 및 값이 할당 됩니다.

## <a name="requirements"></a>요구 사항

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

 **헤더:** WMINet_Utils.idl

 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
