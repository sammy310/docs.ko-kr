---
description: '자세히 알아보기: ICorDebugFunction:: CreateBreakpoint 메서드'
title: ICorDebugFunction::CreateBreakpoint 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
ms.openlocfilehash: 4d55a818352ff98b67c95d5ef15417f2e9e64d40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692630"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a>ICorDebugFunction::CreateBreakpoint 메서드

이 함수의 시작 부분에 중단점을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppBreakpoint`  
 제한이 함수의 새 중단점을 나타내는 ICorDebugFunctionBreakpoint 개체의 주소에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
