---
title: 검증클라이언트키 기능(관리되지 않는 API 참조)
description: VerifyClientKey 기능은 클라이언트 키에 올바른 보안을 보장합니다.
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
ms.openlocfilehash: ebb794240494deb0c831b50e95461ec52017a215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176710"
---
# <a name="verifyclientkey-function"></a>검증클라이언트키 기능
클라이언트 키가 올바른 보안을 유지하는지 확인합니다.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a>반환 값

함수가 성공하면 반환 값은 `ERROR_SUCCESS` (0)입니다.

함수가 실패하면 반환 값은 *WinError.h에*정의된 0이 아닌 오류 코드입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.def  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
