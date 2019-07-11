---
title: NextMethod 함수 (관리 되지 않는 API 참조)
description: NextMethod 함수 열거형의 다음 메서드를 검색합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a730947b0c962d801975917cdf752136e7221c4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746482"
---
# <a name="nextmethod-function"></a>NextMethod 함수
에 대 한 호출을 시작 하는 열거형의 다음 메서드를 검색 [BeginMethodEnumeration](beginmethodenumeration.md)합니다.  

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
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`lFlags`  
[in] 예약되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pName`  
[out] 가리키는 포인터 `null` 호출 하기 전에 합니다. 반환 될 때 함수의 새 주소 `BSTR` 메서드 이름이 들어 있는입니다. 

`ppSignatureIn`  
[out] 에 대 한 포인터를 받는 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포함 하는 `in` 메서드의 매개 변수입니다. 

`ppSignatureOut`  
[out] 에 대 한 포인터를 받는 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포함 하는 `out` 메서드의 매개 변수입니다. 

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | 에 대 한 호출이 없습니다 합니다 [ `BeginEnumeration` ](beginenumeration.md) 함수입니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 열거형에 더 많은 속성이 있습니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 메서드.

호출자가 호출 하 여 열거형 시퀀스를 시작 합니다 [BeginMethodEnumeration](beginmethodenumeration.md) 함수 및 함수 반환 될 때까지 [NextMethod] 함수 호출 `WBEM_S_NO_MORE_DATA`합니다. 호출자가 호출 하 여 시퀀스를 완료 하는 필요에 따라 [EndMethodEnumeration](endmethodenumeration.md)합니다. 호출자에 게 해지할 수 있습니다 열거형 초기 호출 하 여 [EndMethodEnumeration](endmethodenumeration.md) 언제 든 지 합니다.

## <a name="example"></a>예제

에 대 한는 C++ 예제를 참조 합니다 [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 메서드.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
