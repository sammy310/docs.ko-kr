---
title: _EFN_GetManagedObjectName 함수
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
ms.openlocfilehash: c7333f8f7b95655ac821e9a2977d5db3794486a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123002"
---
# <a name="_efn_getmanagedobjectname-function"></a>\_EFN\_GetManagedObjectName 함수
제공 된 관리 되는 개체 포인터를 사용 하 여 형식의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `Client`  
 진행 디버그 클라이언트에 대 한 포인터입니다.  
  
 `objAddr`  
 진행 관리 되는 개체 포인터입니다.  
  
 버퍼가  
 제한이 형식의 이름입니다.  
  
 `cbName`  
 제한이 문자열 버퍼에서 사용할 수 있는 문자 수입니다.  
  
## <a name="remarks"></a>주의  
 현재 컨텍스트에 있는 스레드에 관리 코드가 없으면 함수는 기능 값 0xa0 및 0x1000 오류 코드와 함께 HRESULT SOS_E_NOMANAGEDCODE를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** SOS_Stacktrace  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 전역 정적 함수](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
