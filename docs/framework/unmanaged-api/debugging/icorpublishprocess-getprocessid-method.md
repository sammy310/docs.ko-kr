---
title: ICorPublishProcess::GetProcessID 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: 4cc6bbde2c7367c1109ca73e66f2670a56b2cdbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790550"
---
# <a name="icorpublishprocessgetprocessid-method"></a>ICorPublishProcess::GetProcessID 메서드
이 프로세스에 대 한 운영 체제 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pid`  
 제한이 이 [ICorPublishProcess](icorpublishprocess-interface.md) 개체가 나타내는 프로세스의 식별자에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorPublishProcess 인터페이스](icorpublishprocess-interface.md)
