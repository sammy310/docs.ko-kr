---
description: '자세히 알아보기: ICorDebugRemoteTarget 인터페이스'
title: ICorDebugRemoteTarget 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
ms.openlocfilehash: c6567ebb76c7a3c415c9978dc50941cb0b8985a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717877"
---
# <a name="icordebugremotetarget-interface"></a>ICorDebugRemoteTarget 인터페이스

개발자가 CLR(공용 언어 런타임) 환경에서 Silverlight 기반 애플리케이션을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ICorDebugRemoteTarget::GetHostName 메서드](icordebugremotetarget-gethostname-method.md)|원격 컴퓨터의 IP 주소나 호스트 이름을 반환합니다.|  
  
## <a name="remarks"></a>설명  

 Windows 95, Windows 98, Windows ME 또는 x86이 아닌 플랫폼(IA-64, AMD64 등)에서는 관리 코드와 네이티브 코드가 혼합된 혼합 모드에서의 디버깅이 지원되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug .idl  
  
 **Library:** : corguids .lib  
  
 **.NET Framework 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugRemote 인터페이스](icordebugremote-interface.md)
- [ICorDebug 인터페이스](icordebug-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
