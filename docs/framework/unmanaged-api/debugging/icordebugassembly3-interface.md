---
description: '자세히 알아보기: ICorDebugAssembly3 인터페이스'
title: ICorDebugAssembly3 인터페이스
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 3a8cabf41dffa75d82c2b6fde53dff2ede4838e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791506"
---
# <a name="icordebugassembly3-interface"></a>ICorDebugAssembly3 인터페이스

컨테이너 어셈블리 및 해당 포함된 어셈블리에 대한 지원을 제공하기 위해 ICorDebugAssembly 인터페이스를 확장합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateContainedAssemblies 메서드](icordebugassembly3-enumeratecontainedassemblies-method.md)|이 어셈블리에 포함된 어셈블리에 대한 열거자를 가져옵니다.|  
|[GetContainerAssembly 메서드](icordebugassembly3-getcontainerassembly-method.md)|이 `ICorDebugAssembly3` 개체의 컨테이너 어셈블리를 반환합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다. .NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
