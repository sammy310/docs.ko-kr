---
description: '자세히 알아보기: ICorPublishAppDomainEnum 인터페이스'
title: ICorPublishAppDomainEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: 4e84af576103a792308fd44f903f2ae4daa5d736
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721790"
---
# <a name="icorpublishappdomainenum-interface"></a>ICorPublishAppDomainEnum 인터페이스

프로세스 내에 현재 존재 하는 [ICorPublishAppDomain](icorpublishappdomain-interface.md) 개체의 컬렉션을 순회 하는 메서드를 제공 하는 [ICorPublishEnum](icorpublishenum-interface.md) 인터페이스의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Next 메서드](icorpublishappdomainenum-next-method.md)|`ICorPublishAppDomain`현재 위치에서 시작 하 여 컬렉션에서 지정 된 수의 인스턴스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  

 `ICorPublishAppDomainEnum`인터페이스는 추상 인터페이스인 [ICorPublishEnum](icorpublishenum-interface.md)의 메서드를 구현 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [CorpubPublish Coclass](corpubpublish-coclass.md)
