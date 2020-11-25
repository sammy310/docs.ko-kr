---
title: ICorDebugStaticFieldSymbol 인터페이스
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: fcf3bb61ccd903f2dd375e638814247a98aaf7b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717567"
---
# <a name="icordebugstaticfieldsymbol-interface"></a>ICorDebugStaticFieldSymbol 인터페이스

정적 필드에 대한 디버그 기호 정보를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAddress 메서드](icordebugstaticfieldsymbol-getaddress-method.md)|정적 필드의 주소를 가져옵니다.|  
|[GetName 메서드](icordebugstaticfieldsymbol-getname-method.md)|정적 필드의 이름을 가져옵니다.|  
|[GetSize 메서드](icordebugstaticfieldsymbol-getsize-method.md)|정적 필드의 크기(바이트)를 가져옵니다.|  
  
## <a name="remarks"></a>설명  

 `ICorDebugStaticFieldSymbol` 인터페이스는 정적 필드에 대한 디버그 기호 정보를 검색하는 데 사용됩니다.  
  
> [!NOTE]
> 이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다. .NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugInstanceFieldSymbol 인터페이스](icordebuginstancefieldsymbol-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
