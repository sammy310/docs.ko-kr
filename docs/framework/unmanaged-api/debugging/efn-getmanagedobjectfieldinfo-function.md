---
title: _EFN_GetManagedObjectFieldInfo 함수
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: 182424632e4f81dfdf86e87dc6bb2c75c2780fce
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793768"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a>\_EFN\_GetManagedObjectFieldInfo 함수
제공된 개체 포인터와 필드 이름을 사용하여 개체 시작부터 필드 및 필드 값까지의 오프셋을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `Client`  
 진행 디버그 클라이언트에 대 한 포인터입니다.  
  
 `objAddr`  
 진행 관리 되는 개체 포인터입니다.  
  
 szFieldName  
 진행 필드 이름에 대 한 관리 되는 개체 포인터입니다.  
  
 `pValue`  
 제한이 필드 값입니다. 이 매개 변수는 null일 수 있습니다.  
  
 `pOffset`  
 제한이 `objAddr`에서 필드로의 오프셋입니다. 이 매개 변수는 null일 수 있습니다.  
  
## <a name="remarks"></a>주의  
 오프셋이 0 이면 오프셋이 기록 되지 않습니다.  
  
 현재 컨텍스트에 있는 스레드에 관리 코드가 없는 경우 함수는 기능 값 0xa0 및 0x1000 오류 코드를 사용 하 여 HRESULT SOS_E_NOMANAGEDCODE을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** SOS_Stacktrace. h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 전역 정적 함수](debugging-global-static-functions.md)
