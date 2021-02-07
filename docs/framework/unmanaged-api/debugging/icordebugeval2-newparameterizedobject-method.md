---
description: '자세히 알아보기: ICorDebugEval2:: NewParameterizedObject 메서드'
title: ICorDebugEval2::NewParameterizedObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
ms.openlocfilehash: 2dc746fdada0e79044a1387bd4cb1c11b81d7777
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693683"
---
# <a name="icordebugeval2newparameterizedobject-method"></a>ICorDebugEval2::NewParameterizedObject 메서드

매개 변수가 있는 새 형식 개체를 인스턴스화하고 개체의 생성자 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pConstructor`  
 진행 인스턴스화할 개체의 생성자를 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.  
  
 `nTypeArgs`  
 진행 전달 된 형식 인수의 수입니다.  
  
 `ppTypeArgs`  
 진행 각각 인스턴스화되는 개체에 대 한 형식 인수를 나타내는 ICorDebugType 개체를 가리키는 포인터의 배열입니다.  
  
 `nArgs`  
 진행 생성자에 전달 되는 인수 수입니다.  
  
 `ppArgs`  
 진행 각각 생성자에 전달 되는 인수 값을 나타내는 ICorDebugValue 개체를 가리키는 포인터의 배열입니다.  
  
## <a name="remarks"></a>설명  

 개체의 생성자는 매개 변수를 사용할 수 있습니다 <xref:System.Type> .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
