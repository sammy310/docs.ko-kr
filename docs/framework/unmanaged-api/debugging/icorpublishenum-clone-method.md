---
description: '자세히 알아보기: ICorPublishEnum:: Clone 메서드'
title: ICorPublishEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: 6001f27451afdb564da6275a31256ac348bc693a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721647"
---
# <a name="icorpublishenumclone-method"></a>ICorPublishEnum::Clone 메서드

이 [ICorPublishEnum](icorpublishenum-interface.md) 개체의 복사본을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppEnum`  
 제한이 `ICorPublishEnum` 이 개체의 복사본 인 개체의 주소에 대 한 포인터입니다 `ICorPublishEnum` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorPublishEnum 인터페이스](icorpublishenum-interface.md)
