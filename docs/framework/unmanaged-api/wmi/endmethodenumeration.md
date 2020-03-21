---
title: 엔드메소메이션 함수(관리되지 않는 API 참조)
description: EndMethodEnumeration 함수는 메서드 열거 순서를 종료합니다.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175007"
---
# <a name="endmethodenumeration-function"></a>EndMethodEnumeration 함수
[BeginMethodEnumeration 함수에](beginmethodenumeration.md)대한 호출로 시작된 열거 시퀀스를 종료합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | 0x8004101d | 내부 오류가 발생했습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) 메서드에 대한 호출을 래핑합니다.

호출자는 [BeginMethodEnumeration 함수를](beginmethodenumeration.md)사용하여 열거 시퀀스를 시작한 다음 메서드가 `WBEM_S_NO_MORE_DATA`반환될 때까지 [NextMethod 함수를](nextmethod.md )호출합니다. 호출자는 선택적으로 를 호출하여 `EndMethodEnumeration`시퀀스를 완료합니다. 호출자는 언제든지 호출하여 `EndMethodEnumeration` 열거를 조기에 종료할 수 있습니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
