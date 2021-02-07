---
description: '자세히 알아보기: ICorDebugClass:: GetStaticFieldValue 메서드'
title: ICorDebugClass::GetStaticFieldValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
ms.openlocfilehash: a5406e44491ce89030731c35752066e4943cebfc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711524"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>ICorDebugClass::GetStaticFieldValue 메서드

지정 된 정적 필드의 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `fieldDef`  
 진행 `Def` 검색할 필드를 참조 하는 필드 토큰입니다.  
  
 `pFrame`  
 진행 스레드, 컨텍스트 또는 응용 프로그램 도메인 정적을 명확 하 게 구분 하는 데 사용할 프레임을 나타내는 ICorDebugFrame 개체에 대 한 포인터입니다.  
  
 정적 필드가 스레드, 컨텍스트 또는 응용 프로그램 도메인을 기준으로 하는 경우 프레임에 적절 한 값이 결정 됩니다.  
  
 `ppValue`  
 제한이 정적 필드의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 매개 변수가 있는 형식의 경우 정적 필드의 값은 특정 인스턴스화를 기준으로 합니다. 따라서 클래스 생성자가 형식의 매개 변수를 사용 하는 경우 <xref:System.Type> 대신 [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) 를 호출 `ICorDebugClass::GetStaticFieldValue` 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
