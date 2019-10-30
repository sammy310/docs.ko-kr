---
title: _EFN_GetManagedExcepStack 함수
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
ms.openlocfilehash: 9bcc03cc97a62b4c1cadacd7c0b2bc46b9fec470
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134136"
---
# <a name="_efn_getmanagedexcepstack-function"></a>\_EFN\_GetManagedExcepStack 함수
관리되는 예외 개체 주소를 제공하면 내부에 포함된 스택 추적의 문자열 버전을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `Client`  
 진행 디버깅 중인 클라이언트입니다.  
  
 `StackObjAddr`  
 진행 <xref:System.Exception>에서 파생 된 관리 되는 개체 포인터입니다.  
  
 szStackString  
 제한이 반환 된 문자열입니다.  
  
 `cbString`  
 제한이 문자열 버퍼에서 사용할 수 있는 문자 수입니다.  
  
## <a name="remarks"></a>주의  
 현재 컨텍스트에 있는 스레드에 관리 코드가 없으면 함수는 기능 값 0xa0 및 0x1000 오류 코드와 함께 HRESULT SOS_E_NOMANAGEDCODE를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** SOS_Stacktrace  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 전역 정적 함수](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
