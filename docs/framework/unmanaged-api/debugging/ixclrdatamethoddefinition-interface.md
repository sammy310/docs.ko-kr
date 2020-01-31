---
title: IXCLRDataMethodDefinition 인터페이스
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790420"
---
# <a name="ixclrdatamethoddefinition-interface"></a>IXCLRDataMethodDefinition 인터페이스

메서드 정의에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>메서드

다음 메서드는 인터페이스에서 사용할 수 있는 몇 가지 메서드입니다.

| 메서드                                                                                                                          | 설명                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [StartEnumInstances](ixclrdatamethoddefinition-startenuminstances-method.md) | 지정 된 `IXCLRDataAppDomain`에 대 한 메서드 인스턴스의 열거형 핸들을 제공 합니다. |
| [EnumInstance](ixclrdatamethoddefinition-enuminstance-method.md)             | 이 메서드 정의의 인스턴스를 열거 합니다.                                         |
| [EndEnumInstances](ixclrdatamethoddefinition-endenuminstances-method.md)     | 인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.         |

## <a name="remarks"></a>주의

이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다. 그러나 일반적인 COM 메커니즘을 통해 가져올 수 있는 GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97`를 사용 하 여 `IUnknown`에서 파생 되는 COM 인터페이스입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참조

- [디버깅](index.md)
- [디버깅 인터페이스](debugging-interfaces.md)
