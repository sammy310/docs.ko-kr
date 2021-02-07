---
description: '자세히 알아보기: ICorDebugEval:: NewObjectNoConstructor 메서드'
title: ICorDebugEval::NewObjectNoConstructor 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
ms.openlocfilehash: 4bc8f95da1a554091052dc7e7f49aef4f494578d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693813"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a>ICorDebugEval::NewObjectNoConstructor 메서드

생성자 메서드 호출을 시도 하지 않고 지정 된 형식의 새 개체 인스턴스를 할당 합니다.  
  
 이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다. 대신 [ICorDebugEval2:: NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) 를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pClass`  
 진행 인스턴스화할 개체의 형식을 나타내는 ICorDebugClass 개체에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.1, 1.0  
  
## <a name="see-also"></a>참고 항목

- [NewParameterizedObjectNoConstructor 메서드](icordebugeval2-newparameterizedobjectnoconstructor-method.md)
