---
title: IXCLRDataProcess 인터페이스
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 6a6def8fc10f04b89aa8d8c735025b01f9b6ddfb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420762"
---
# <a name="ixclrdataprocess-interface"></a>IXCLRDataProcess 인터페이스

프로세스에 대 한 정보를 쿼리 하는 메서드를 제공 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>메서드

| 메서드                                                                                                                                               | 설명                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | `AppDomain`프로세스의 고유 id로를 가져옵니다.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | 프로세스의 모듈을 열거 하는 핸들을 제공 합니다.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | 이 프로세스의 모듈을 열거 합니다.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | 모듈 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | 지정 된 주소에서 시작 하는의 메서드 인스턴스를 열거 하는 핸들을 제공 합니다 `AppDomain` . |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | 주소 오프셋에서 시작 하 여이 프로세스의 메서드 인스턴스를 열거 합니다.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | 인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.             |

## <a name="remarks"></a>설명

이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다. 그러나 `IUnknown` `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [디버깅 인터페이스](debugging-interfaces.md)
