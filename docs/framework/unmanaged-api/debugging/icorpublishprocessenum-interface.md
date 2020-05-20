---
title: ICorPublishProcessEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 657d2d638a419ba88d4cf7152f4505de1bd23706
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421074"
---
# <a name="icorpublishprocessenum-interface"></a>ICorPublishProcessEnum 인터페이스
[ICorPublishProcess](icorpublishprocess-interface.md) 개체의 컬렉션을 순회 하는 메서드를 제공 하는 [ICorPublishEnum](icorpublishenum-interface.md) 인터페이스의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Next 메서드](icorpublishprocessenum-next-method.md)|`ICorPublishProcess`현재 위치에서 시작 하 여 컬렉션에서 지정 된 수의 인스턴스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 `ICorPublishProcessEnum`인터페이스는 추상 인터페이스인 [ICorPublishEnum](icorpublishenum-interface.md)의 메서드를 구현 합니다.  
  
 `ICorPublishProcessEnum` [ICorPublish:: enumprocesses](icorpublish-enumprocesses-method.md) 메서드로 인스턴스를 만듭니다. 개체의 컬렉션을 순회 하는 `ICorPublishProcess` 것은 인스턴스가 만들어질 때 지정 된 필터 조건을 기반으로 합니다 `ICorPublishProcessEnum` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [CorpubPublish Coclass](corpubpublish-coclass.md)
