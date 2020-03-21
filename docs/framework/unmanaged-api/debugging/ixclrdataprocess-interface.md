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
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178366"
---
# <a name="ixclrdataprocess-interface"></a>IXCLRDataProcess 인터페이스

프로세스에 대한 정보를 쿼리하는 메서드를 제공합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>메서드

| 방법                                                                                                                                               | Description                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | 고유 `AppDomain` ID로 프로세스를 가져옵니다.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | 프로세스모듈을 등록하는 핸들을 제공합니다.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | 이 프로세스의 모듈을 개과시합니다.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | 모듈 열거 중에 사용되는 내부 거처에서 사용하는 리소스를 해제합니다.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | 지정된 주소에서 `AppDomain` 시작하는 메서드 인스턴스를 등록하는 핸들을 제공합니다. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | 주소 오프셋에서 시작하는 이 프로세스의 메서드 인스턴스를 모두보대해서는                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | 인스턴스 열거 중에 사용되는 내부 거처에서 사용하는 리소스를 해제합니다.             |

## <a name="remarks"></a>설명

이 인터페이스는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출되지 않습니다. 그러나 일반적인 COM 메커니즘을 통해 얻을 `IUnknown` 수 `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 있는 GUID를 사용하여 파생되는 COM 인터페이스입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.
**헤더:** 없음  
**라이브러리:** 없음  
**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [디버깅 인터페이스](debugging-interfaces.md)
