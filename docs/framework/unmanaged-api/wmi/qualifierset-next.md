---
title: QualifierSet_Next 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Next 함수 열거형의 다음 한정자를 검색합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ac5cc8633881749bdc167e1b3925a83f7adf3b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760294"
---
# <a name="qualifiersetnext-function"></a>QualifierSet_Next 함수
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

`vFunc`   
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`   
[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.

`lFlags`   
[in] 예약되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pstrName`   
[out] 한정자의 이름입니다. 하는 경우 `null`,이 매개 변수는 무시 되 고, 그렇지 않으면 `pstrName` 유효한 가리키지 해야 `BSTR` 또는 메모리 누수가 발생 합니다. Null이 아닌 함수 항상 할당 하는 새 `BSTR` 반환 하는 경우 `WBEM_S_NO_ERROR`합니다.

`pVal`   
[out] 성공 하면 한정자의 값입니다. 함수가 실패 한 경우는 `VARIANT` 가리키는 `pVal` 수정 되지 않습니다. 이 매개 변수가 `null`, 매개 변수는 무시 됩니다.

`plFlavor`   
[out] 긴 한정자 버전을 수신 하는 포인터입니다. 버전 정보는 적절 하지 않으면이 매개 변수 수 `null`입니다. 

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못 되었습니다. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 호출자에 게 호출 하지 않았습니다 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)합니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 새 열거형 시작에 사용할 있는 메모리가 충분 하지 않습니다. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 한정자가 자세한 열거형에 남아 있습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) 메서드.

호출 된 `QualifierSet_Next` 함수는 반환 될 때까지 모든 한정자 열거를 반복적으로 `WBEM_S_NO_MORE_DATA`입니다. 열거형을 조기에 종료를 호출 합니다 [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) 함수입니다.

열거 동안 반환 되는 한정자가 순서 정의 되지 않습니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
