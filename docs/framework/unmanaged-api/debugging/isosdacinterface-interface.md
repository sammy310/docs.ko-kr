---
title: ISOSDacInterface 인터페이스
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c9b4e6e5b36fe38b6c0ea78f6d1848d155008bcc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420970"
---
# <a name="isosdacinterface-interface"></a>ISOSDacInterface 인터페이스

에서 데이터에 액세스 하는 도우미 메서드를 제공 `SOS` 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>메서드

| 메서드                                                                                                               | 설명                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [GetMethodDescData](isosdacinterface-getmethoddescdata-method.md) | 지정 된 MethodDesc 포인터에 대 한 데이터를 가져옵니다. |
| [GetMethodDescPtrFromIP](isosdacinterface-getmethoddescptrfromip-method.md) | 지정 된 기본 명령 주소를 포함 하는 메서드에 해당 하는 MethodDesc의 포인터를 검색 합니다. |
| [GetModuleData](isosdacinterface-getmoduledata-method.md)| 지정 된 주소에서 로드 된 모듈에 해당 하는 데이터를 인출 합니다. |

## <a name="remarks"></a>설명

이 인터페이스는 런타임 내부에 있고 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다. 그러나 `IUnknown` `436f00f2-b42a-4b9f-870c-e73db66ae930` 일반적인 com 메커니즘을 통해 가져올 수 있는 GUID를 사용 하 여에서 파생 되는 COM 인터페이스입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [디버깅 인터페이스](debugging-interfaces.md)
