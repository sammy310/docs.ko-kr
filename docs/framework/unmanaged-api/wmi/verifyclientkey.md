---
title: VerifyClientKey 함수 (관리 되지 않는 API 참조)
description: VerifyClientKey 함수는 클라이언트 키의 보안이 올바른지 확인 합니다.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 26cffe9936f2e01078b6f54e8499b58519f1018e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729423"
---
# <a name="verifyclientkey-function"></a>VerifyClientKey 함수

클라이언트 키가 올바른 보안을 유지하는지 확인합니다.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 `ERROR_SUCCESS` (0)입니다.

함수가 실패 하면 반환 값은 *winerror.h* 에 정의 된 0이 아닌 오류 코드입니다.

## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils .def  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참조

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
