---
title: ICorDebugILFrame::EnumerateArguments 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: d74c5a6f966201c8ca9d2854de2e9986e7f1d0fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131036"
---
# <a name="icordebugilframeenumeratearguments-method"></a>ICorDebugILFrame::EnumerateArguments 메서드
이 프레임의 인수에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppValueEnum`  
 제한이 이 프레임의 인수에 대 한 열거자 인 ICorDebugValueEnum 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `EnumerateArguments`이 ICorDebugILFrame 개체가 나타내는 호출 프레임에서 사용할 수 있는 인수를 나열할 수 있는 열거자를 가져옵니다. 이 목록에는 `vararg`되지 않은 인수 뿐만 아니라 [vararg](/cpp/windows/vararg) (인수 개수) 인 인수가 포함 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
