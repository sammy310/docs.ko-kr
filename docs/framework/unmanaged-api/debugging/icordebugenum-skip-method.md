---
description: '자세히 알아보기: ICorDebugEnum:: Skip 메서드'
title: ICorDebugEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: f72e400b3c2c911f609aca19f1b7d6a3a4e785cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694359"
---
# <a name="icordebugenumskip-method"></a>ICorDebugEnum::Skip 메서드

지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `celt`  
 진행 커서를 앞으로 이동 하는 기준이 되는 항목의 수입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugEnum 인터페이스](icordebugenum-interface1.md)
