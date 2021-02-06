---
description: '자세히 알아보기: ICorDebugProcess2:: GetReferenceValueFromGCHandle 메서드'
title: ICorDebugProcess2::GetReferenceValueFromGCHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
ms.openlocfilehash: 02047dee9116d34a365242f2a532766eb60e1c81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650224"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle 메서드

가비지 수집 핸들이 있는 지정 된 관리 되는 개체에 대 한 참조 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `handle`  
 진행 가비지 수집 핸들이 있는 관리 되는 개체에 대 한 포인터입니다. 이 값은 <xref:System.IntPtr> 개체 이며 <xref:System.Runtime.InteropServices.GCHandle> 관리 되는 개체에 대 한에서 검색할 수 있습니다.  
  
 `pOutValue`  
 제한이 지정 된 관리 되는 개체에 대 한 참조를 나타내는 ICorDebugReferenceValue 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 반환 된 참조 값과 가비지 수집 참조 값을 혼동 하지 마십시오.  
  
 반환 된 참조는 일반 참조 처럼 동작 합니다. 중단점 후 코드 실행이 계속 되 면 사용할 수 없습니다. 대상 개체의 수명은 참조 값의 수명에 영향을 받지 않습니다.  
  
> [!NOTE]
> `GetReferenceValueFromGCHandle`이 메서드는 핸들의 유효성을 검사 하지 않습니다. 따라서 메서드는 `GetReferenceValueFromGCHandle` 잘못 된 핸들이 전달 될 경우 디버거 및 디버깅 중인 코드를 모두 손상 시킬 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
