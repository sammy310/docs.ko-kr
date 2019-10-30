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
ms.openlocfilehash: 7d083655326333f18ee98f8e84fff2ed182dde6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103456"
---
# <a name="icorpublishenum-interface"></a>ICorPublishEnum 인터페이스
프로세스 및 응용 프로그램 도메인에 대 한 정보를 게시 하는 데 사용 되는 열거자에 대 한 추상 기본 인터페이스로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Clone 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|이 `ICorPublishEnum` 개체의 복사본을 만듭니다.|  
|[GetCount 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|열거형의 항목 수를 가져옵니다.|  
|[Reset 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|커서를 열거형의 시작 부분으로 이동 합니다.|  
|[Skip 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.|  
  
## <a name="remarks"></a>주의  
 다음 열거자는 `ICorPublishEnum`에서 파생 됩니다.  
  
- [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [CorpubPublish Coclass](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
