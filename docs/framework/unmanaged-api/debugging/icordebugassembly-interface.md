---
description: '자세히 알아보기: ICorDebugAssembly 인터페이스'
title: ICorDebugAssembly 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: 746b5f4b2f26550788708d93bf0dd50f5f495041
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711949"
---
# <a name="icordebugassembly-interface"></a>ICorDebugAssembly 인터페이스

어셈블리를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateModules 메서드](icordebugassembly-enumeratemodules-method.md)|어셈블리에 포함 된 모듈의 열거자를 가져옵니다.|  
|[GetAppDomain 메서드](icordebugassembly-getappdomain-method.md)|이 인스턴스를 포함 하는 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugAssembly` .|  
|[GetCodeBase 메서드](icordebugassembly-getcodebase-method.md)|현재 버전의 .NET Framework에서 구현 되지 않았습니다.|  
|[GetName 메서드](icordebugassembly-getname-method.md)|어셈블리의 이름을 가져옵니다.|  
|[GetProcess 메서드](icordebugassembly-getprocess-method.md)|어셈블리가 실행 되는 ICorDebugProcess 인스턴스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
