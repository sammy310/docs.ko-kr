---
description: '자세히 알아보기: ICorDebugILFrame:: GetLocalVariable 메서드'
title: ICorDebugILFrame::GetLocalVariable 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
ms.openlocfilehash: c4bb3e5a5d970539607efbaf55f3f7f08f7e72af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791376"
---
# <a name="icordebugilframegetlocalvariable-method"></a>ICorDebugILFrame::GetLocalVariable 메서드

이 MSIL (Microsoft 중간 언어) 스택 프레임에서 지정 된 지역 변수의 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwIndex`  
 진행 이 MSIL 스택 프레임에 있는 지역 변수의 인덱스입니다.  
  
 `ppValue`  
 [out] 검색된 값을 나타내는 ICorDebugValue 개체의 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `GetLocalVariable`메서드는 MSIL 스택 프레임 또는 JIT (just-in-time) 컴파일된 프레임에서 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
