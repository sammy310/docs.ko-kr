---
description: '자세히 알아보기: ICorDebugAssembly:: GetName 메서드'
title: ICorDebugAssembly::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
ms.openlocfilehash: c2ffa910eaf97c5539a33dbcd3486b7dfb117b51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711988"
---
# <a name="icordebugassemblygetname-method"></a>ICorDebugAssembly::GetName 메서드

이 인스턴스가 나타내는 어셈블리의 이름을 가져옵니다 `ICorDebugAssembly` .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `cchName`  
 [in] `szName` 배열의 크기입니다.  
  
 `pcchName`  
 제한이 이름의 실제 길이를 지정 하는 정수에 대 한 포인터입니다.  
  
 `szName`  
 제한이 이름을 저장 하는 배열입니다.  
  
## <a name="remarks"></a>설명  

 `GetName`메서드는 어셈블리의 전체 경로 및 파일 이름을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
