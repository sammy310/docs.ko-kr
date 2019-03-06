---
title: ICorDebugClass::GetToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7532c34dca070b07bd3124002eaf72a2f939238
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493065"
---
# <a name="icordebugclassgettoken-method"></a>ICorDebugClass::GetToken 메서드
가져옵니다는 `TypeDef` 이 클래스의 정의 참조 하는 메타 데이터 토큰입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pTypeDef`  
 [out] 에 대 한 포인터는 `mdTypeDef` 이 클래스의 정의 참조 하는 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
