---
title: 재설정 보안 기능(관리되지 않는 API 참조)
description: ResetSecurity 함수는 현재 스레드에 가장 토큰을 할당합니다.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: ce74494455c6cc7fe382a4ea4ef2ff0c4e98c61b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174864"
---
# <a name="resetsecurity-function"></a>ResetSecurity 함수
제공된 가장 토큰을 현재 스레드에 할당합니다.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a>매개 변수

`token`  
【인】 현재 스레드와 연결할 가장 토큰입니다. 이 값은 `null`일 수 있습니다.

## <a name="return-value"></a>반환 값

함수가 성공하면 반환 값은 `S_OK` (0)입니다.

함수가 실패하면 반환 값은 0이 아닌 오류 코드입니다. 확장 오류 정보를 얻으려면 [GetErrorInfo](geterrorinfo.md) 함수를 호출합니다.
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
