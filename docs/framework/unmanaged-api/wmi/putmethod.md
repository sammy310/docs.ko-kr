---
title: PutMethod 함수(관리되지 않는 API 참조)
description: PutMethod 함수는 메서드를 만듭니다.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174916"
---
# <a name="putmethod-function"></a>PutMethod 함수
메서드를 만듭니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`wszName`  
【인】 만들 메서드의 이름입니다.

`lFlags`  
[in] 예약되어 있습니다. 이 매개변수는 0이어야 합니다.

`pSignatureIn`  
【인】 메서드에 대 한 `in` 매개 변수를 포함 하는 __Parameters 시스템 [클래스의](/windows/desktop/WmiSdk/--parameters) 복사본에 대 한 포인터입니다. 로 설정하면 이 `null`매개 변수가 무시됩니다.  

`pSignatureOut`  
【인】  메서드에 대 한 `out` 매개 변수를 포함 하는 __Parameters 시스템 [클래스의](/windows/desktop/WmiSdk/--parameters) 복사본에 대 한 포인터입니다. 로 설정하면 이 `null`매개 변수가 무시됩니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 잘못되었습니다. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | `[in, out]` *pInSignature* 및 *pOutSignature* 개체모두에 지정된 메서드 매개 변수에는 서로 다른 한정자가 있습니다.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | 메서드 매개 변수가 **ID** 한정자의 사양을 누락되었습니다. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | 메서드 매개 변수에 할당된 ID 계열이 연속적이지 않거나 0에서 시작되지 않습니다. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | 메서드의 반환 값에는 **ID** 한정자가 있습니다. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | 부모 클래스에서 기존 메서드 이름을 다시 사용하려고 시도했으며 서명이 일치하지 않습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다. |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) 메서드에 대한 호출을 래핑합니다.

이 메서드 호출은 `ptr` CIM 클래스 정의인 경우에만 지원됩니다. CIM 인스턴스를 가리키는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포인터에서 메서드 조작을 사용할 수 없습니다.

사용자는 밑줄로 시작하거나 끝나는 이름으로 메서드를 만들 수 없습니다. 시스템 클래스 및 속성에 대해 예약되어 있습니다.

메서드의 경우 `in` 및 `out` 매개 변수는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 개체의 속성으로 설명됩니다.

매개 `[in/out]` 변수는 `pInSignature` 매개 변수와 `pOutSignature` 매개 변수가 가리키는 두 개체에 동일한 속성을 추가하여 정의할 수 있습니다. 이 경우 속성은 동일한 **ID** 한정자 값을 공유합니다.

[__Parameters](/windows/desktop/WmiSdk/--parameters) 클래스 개체의 각 `ReturnValue` 속성에는 매개 변수가 나타나는 순서를 식별하는 0기반 숫자 값인 **ID** 한정자가 있어야 합니다. 두 매개 변수가 동일한 **ID** 값을 가질 수 없으며 **ID** 값을 건너뛸 수 없습니다. 두 조건 중 `PutMethod` 하나가 `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`발생하면 함수가 반환됩니다.

## <a name="example"></a>예제

예를 들어 [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) 메서드를 참조하십시오.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
