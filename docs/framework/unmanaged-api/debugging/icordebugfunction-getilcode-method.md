---
title: ICorDebugFunction::GetILCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f34a2fe2bb1f92e75f77c086b03776ec59495600
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995750"
---
# <a name="icordebugfunctiongetilcode-method"></a>ICorDebugFunction::GetILCode 메서드
이 ICorDebugFunction 개체와 연결 된 Microsoft MSIL (intermediate language) 코드를 나타내는 ICorDebugCode 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppCode`  
 [out] 에 대 한 포인터를 `ICorDebugCode` 인스턴스이거나, 함수가 MSIL을 컴파일되지 않은 경우 null입니다.  
  
## <a name="remarks"></a>설명  
 편집 하며 계속 하기가이 함수에 대해 허용 된 경우는 `GetILCode` 메서드는이 함수는 CLR (공용 언어 런타임) 코드의 편집된 버전에 해당 하는 MSIL 코드를 가져옵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
