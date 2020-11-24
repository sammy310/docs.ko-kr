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
ms.openlocfilehash: 0fb694cf85256c0f3ac5ae179e53ff504ab707e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676207"
---
# <a name="_efn_getmanagedobjectname-function"></a>\_EFN \_ GetManagedObjectName 함수

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
  
 szName  
 제한이 형식의 이름입니다.  
  
 `cbName`  
 제한이 문자열 버퍼에서 사용할 수 있는 문자 수입니다.  
  
## <a name="remarks"></a>설명  

 현재 컨텍스트에 있는 스레드에 관리 코드가 없는 경우 함수는 기능 값 0xa0 및 0x1000 오류 코드를 사용 하 여 HRESULT SOS_E_NOMANAGEDCODE을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** SOS_Stacktrace. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 전역 정적 함수](debugging-global-static-functions.md)
