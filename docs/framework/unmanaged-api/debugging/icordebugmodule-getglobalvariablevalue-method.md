---
description: '자세히 알아보기: ICorDebugModule:: GetGlobalVariableValue 메서드'
title: ICorDebugModule::GetGlobalVariableValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
ms.openlocfilehash: a4efe2f56387be7351fd5bc16716bcd1f34f7d7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691668"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a>ICorDebugModule::GetGlobalVariableValue 메서드

지정 된 전역 변수의 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `fieldDef`  
 진행 `mdFieldDef` 전역 변수를 설명 하는 메타 데이터를 참조 하는 토큰입니다.  
  
 `ppValue`  
 제한이 지정 된 전역 변수의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
