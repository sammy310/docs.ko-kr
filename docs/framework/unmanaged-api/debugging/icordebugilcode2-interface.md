---
description: '자세히 알아보기: ICorDebugILCode2 인터페이스'
title: ICorDebugILCode2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: 52e47b8cbf8f9926797e193944fd7e97b2e4dbcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791415"
---
# <a name="icordebugilcode2-interface"></a>ICorDebugILCode2 인터페이스

[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 는 [ICorDebugILCode](icordebugilcode-interface.md) 인터페이스를 논리적으로 확장 하 여 함수의 지역 변수 시그니처에 대 한 토큰을 반환 하는 메서드를 제공 하 고 프로파일러 계측 된 il (중간 언어) 오프셋을 원래 메서드 il 오프셋에 매핑합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetInstrumentedILMap 메서드](icordebugilcode2-getinstrumentedilmap-method.md)|이 인스턴스에 대해 프로파일러가 계측한 IL 오프셋에서 원래 메서드 IL 오프셋으로의 맵을 반환합니다.|  
|[GetLocalVarSigToken 메서드](icordebugilcode2-getlocalvarsigtoken-method.md)|이 인스턴스로 표시되는 함수의 로컬 변수 서명에 대한 메타데이터 토큰을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugILCode 인터페이스](icordebugilcode-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
