---
title: QualifierSet_Get 기능(관리되지 않는 API 참조)
description: QualifierSet_Get 함수는 명명된 한정자를 가져옵니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2f4e2d4518e01f3415b8f17ce5778dd98b2a45c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174890"
---
# <a name="qualifierset_get-function"></a>QualifierSet_Get 함수
지정한 명명된 한정자를 가져옵니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`【인】 이 매개 변수는 사용되지 않습니다.

`ptr`【인】 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대한 포인터입니다.

`wszName`【인】 값이 요청된 한정자의 이름입니다.

`lFlags`【인】 예약. 이 매개변수는 0이어야 합니다.

`pVal`【아웃】 성공하면 한정자에 대한 올바른 형식과 값이 됩니다. 함수가 실패하면 `VARIANT` 가리키는 가리키는 `pVal` 것이 수정되지 않습니다. 이 매개 `null`변수가 이 경우 매개 변수는 무시됩니다.

`plFlavor`【아웃】 요청된 한정자에 대한 한정자 맛 비트를 받는 LONG에 대한 포인터입니다. 풍미 정보가 필요하지 않은 경우 이 `null`매개 변수가 될 수 있습니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못된 경우 |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 한정자가 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) 메서드에 대한 호출을 래핑합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
