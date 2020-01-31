---
title: ICorPublishEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
ms.openlocfilehash: f54bb99df60d7b3fb7bb98de75fbae210597e45c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790620"
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum 인터페이스
프로세스 및 응용 프로그램 도메인에 대 한 정보를 게시 하는 데 사용 되는 열거자에 대 한 추상 기본 인터페이스로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Clone 메서드](icorpublishenum-clone-method.md)|이 복사본을 만들고 `ICorPublishEnum` 개체입니다.|  
|[GetCount 메서드](icorpublishenum-getcount-method.md)|열거형의 항목 수를 가져옵니다.|  
|[Reset 메서드](icorpublishenum-reset-method.md)|커서를 열거형의 시작 부분으로 이동 합니다.|  
|[Skip 메서드](icorpublishenum-skip-method.md)|지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.|  
  
## <a name="remarks"></a>주의  
 다음 열거자는 `ICorPublishEnum`에서 파생 됩니다.  
  
- [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [CorpubPublish Coclass](corpubpublish-coclass.md)
- [디버깅 인터페이스](debugging-interfaces.md)
