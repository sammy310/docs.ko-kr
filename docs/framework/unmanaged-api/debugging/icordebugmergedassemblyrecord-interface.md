---
title: ICorDebugMergedAssemblyRecord 인터페이스
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208722"
---
# <a name="icordebugmergedassemblyrecord-interface"></a>ICorDebugMergedAssemblyRecord 인터페이스
병합된 어셈블리에 대한 정보를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetCulture 메서드](icordebugmergedassemblyrecord-getculture-method.md)|어셈블리의 문화권 이름 문자열을 가져옵니다.|  
|[GetIndex 메서드](icordebugmergedassemblyrecord-getindex-method.md)|어셈블리의 접두사 인덱스를 가져옵니다.|  
|[GetPublicKey 메서드](icordebugmergedassemblyrecord-getpublickey-method.md)|어셈블리의 공개 키를 가져옵니다.|  
|[GetPublicKeyToken 메서드](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|어셈블리의 공개 키 토큰을 가져옵니다.|  
|[GetSimpleName 메서드](icordebugmergedassemblyrecord-getsimplename-method.md)|어셈블리의 단순한 이름을 가져옵니다.|  
|[GetVersion 메서드](icordebugmergedassemblyrecord-getversion-method.md)|어셈블리의 버전 정보를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다. .NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
