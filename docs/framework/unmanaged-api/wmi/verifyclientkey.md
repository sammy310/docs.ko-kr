---
title: VerifyClientKey 함수 (관리 되지 않는 API 참조)
description: VerifyClientKey 함수 클라이언트 키에 올바른 보안을 보장 합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47fee26a0c4c25e4bff5bca94e5e26daaf98cccd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782488"
---
# <a name="verifyclientkey-function"></a>VerifyClientKey 함수
클라이언트 키가 올바른 보안을 유지하는지 확인합니다.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 `ERROR_SUCCESS` (0).

반환 값은 0이 아닌 오류 코드에 정의 된 함수가 실패 한 경우 *WinError.h*합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** WMINet_Utils.def  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
