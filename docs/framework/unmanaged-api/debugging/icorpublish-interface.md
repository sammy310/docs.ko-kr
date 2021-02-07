---
description: '자세히 알아보기: ICorPublish 인터페이스'
title: ICorPublish 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: 0cec1d3407246989c6b916ca0760e6f556566ce6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721829"
---
# <a name="icorpublish-interface"></a>ICorPublish 인터페이스

프로세스에 대 한 정보를 게시 하 고 해당 프로세스의 응용 프로그램 도메인에 대 한 정보를 게시 하기 위한 일반 인터페이스로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumProcesses 메서드](icorpublish-enumprocesses-method.md)|이 컴퓨터에서 실행 되는 관리 되는 프로세스를 포함 하는 [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) 인스턴스를 가져옵니다.|  
|[GetProcess 메서드](icorpublish-getprocess-method.md)|지정 된 식별자를 사용 하 여 프로세스를 나타내는 [ICorPublishProcess](icorpublishprocess-interface.md) 인스턴스를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [CorpubPublish Coclass](corpubpublish-coclass.md)
