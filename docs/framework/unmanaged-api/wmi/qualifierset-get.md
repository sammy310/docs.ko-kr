---
title: QualifierSet_Get 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Get 함수는 명명 된 한정자를 가져옵니다.
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
ms.openlocfilehash: fd096287b85b4a51a8cae85dddcca95cc1a8dbae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721142"
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

`vFunc` 진행 이 매개 변수는 사용 되지 않습니다.

`ptr` 진행 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대 한 포인터입니다.

`wszName` 진행 해당 값이 요청 된 한정자의 이름입니다.

`lFlags` 진행 쓰이는. 이 매개 변수는 0 이어야 합니다.

`pVal` 제한이 성공 하면 한정자의 올바른 형식 및 값입니다. 함수가 실패 하면 `VARIANT` 에서 가리키는가 `pVal` 수정 되지 않습니다. 이 매개 변수가 이면 `null` 매개 변수는 무시 됩니다.

`plFlavor` 제한이 요청 된 한정자에 대 한 한정자 버전 비트를 받는 LONG에 대 한 포인터입니다. 버전 정보를 원하지 않는 경우이 매개 변수는 일 수 있습니다 `null` .

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못된 경우 |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정한 한정자가 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출에 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemQualifierSet:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) 메서드에 대 한 호출을 래핑합니다.

## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils idl  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참조

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
