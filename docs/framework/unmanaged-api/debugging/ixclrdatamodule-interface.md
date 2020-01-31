---
title: IXCLRDataModule 인터페이스
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8757642db6c4375cf55d1f7288669c4c8a752a38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790401"
---
# <a name="ixclrdatamodule-interface"></a>IXCLRDataModule 인터페이스

로드 된 모듈에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>메서드

| 메서드                                                                                                                                | 설명                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [GetMethodDefinitionByToken](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | 지정 된 메타 데이터 토큰에 해당 하는 메서드 정의를 가져옵니다. |
| [요청](ixclrdatamodule-request-method.md)                                       | 모듈의 데이터에 지정 된 버퍼를 채우도록 요청 합니다.       |
| [GetVersionId](ixclrdatamodule-getversionid-method.md)                             | 모듈의 버전 ID를 가져옵니다.                                       |

## <a name="remarks"></a>주의

이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다. 그러나 일반적인 COM 메커니즘을 통해 가져올 수 있는 GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2`를 사용 하 여 `IUnknown`에서 파생 되는 COM 인터페이스입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참조

- [디버깅](index.md)
- [디버깅 인터페이스](debugging-interfaces.md)
