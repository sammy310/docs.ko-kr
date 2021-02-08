---
description: '자세히 알아보기: ICorPublishProcess 인터페이스'
title: ICorPublishProcess 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8dbc619d33c2c9b625dde852948dff00b5be926e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800879"
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess 인터페이스

프로세스에 대해 표시할 정보에 액세스 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumAppDomains 메서드](icorpublishprocess-enumappdomains-method.md)|이에서 참조 하는 프로세스의 응용 프로그램 도메인을 포함 하는 [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) 인스턴스를 가져옵니다 `ICorPublishProcess` .|  
|[GetDisplayName 메서드](icorpublishprocess-getdisplayname-method.md)|이에서 참조 하는 프로세스에 대 한 실행 파일의 전체 경로를 가져옵니다 `ICorPublishProcess` .|  
|[GetProcessID 메서드](icorpublishprocess-getprocessid-method.md)|이에서 참조 하는 프로세스에 대 한 운영 체제 식별자를 가져옵니다 `ICorPublishProcess` .|  
|[IsManaged 메서드](icorpublishprocess-ismanaged-method.md)|이에서 참조 하는 프로세스를 `ICorPublishProcess` 관리 코드를 실행 하는 것으로 알려진 지 여부를 나타내는 값을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [CorpubPublish Coclass](corpubpublish-coclass.md)
