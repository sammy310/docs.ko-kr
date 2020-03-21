---
title: QualifierSet_Next 함수(관리되지 않는 API 참조)
description: QualifierSet_Next 함수는 열거형에서 다음 한정자를 검색합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174877"
---
# <a name="qualifierset_next-function"></a>QualifierSet_Next 함수
[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수를 호출하여 시작된 열거형의 다음 한정자를 검색합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`【인】 이 매개 변수는 사용되지 않습니다.

`ptr`【인】 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대한 포인터입니다.

`lFlags`【인】 예약. 이 매개변수는 0이어야 합니다.

`pstrName`【아웃】 한정자의 이름입니다. 이 `null`매개 변수가 무시되는 경우; 그렇지 `pstrName` 않으면 유효한 `BSTR` 것을 가리키거나 메모리 누수가 발생하도록 하지 않아야 합니다. null이 아닌 경우 함수는 항상 `BSTR` 새 를 `WBEM_S_NO_ERROR`반환할 때 할당합니다.

`pVal`【아웃】 성공하면 한정자의 값입니다. 함수가 실패하면 `VARIANT` 가리키는 가리키는 `pVal` 것이 수정되지 않습니다. 이 매개 `null`변수가 이 경우 매개 변수는 무시됩니다.

`plFlavor`【아웃】 한정자 맛을 받는 LONG에 대한 포인터입니다. 풍미 정보가 필요하지 않은 경우 이 `null`매개 변수가 될 수 있습니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못된 경우 |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 호출자는 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)호출하지 않았습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 새 열거를 시작하기에 사용할 수 있는 메모리가 부족합니다. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 열거형에 더 이상 한정자가 남아 있지 않습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) 메서드에 대한 호출을 래핑합니다.

함수가 `QualifierSet_Next` 반환될 `WBEM_S_NO_MORE_DATA`때까지 모든 한정자를 등록하기 위해 함수를 반복적으로 호출합니다. 열거를 일찍 종료하려면 [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) 함수를 호출합니다.

열거 중에 반환된 한정자의 순서는 정의되지 않습니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
