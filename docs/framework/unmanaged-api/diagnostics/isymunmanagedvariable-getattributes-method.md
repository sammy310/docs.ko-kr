---
title: ISymUnmanagedVariable::GetAttributes 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
ms.openlocfilehash: 29869abdd39f61c6c9cb51d6b2be50fa462c5b70
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615256"
---
# <a name="isymunmanagedvariablegetattributes-method"></a>ISymUnmanagedVariable::GetAttributes 메서드
이 변수에 대 한 특성 플래그를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pRetVal`  
 제한이 특성을 수신 하는에 대 한 포인터 `ULONG32` 입니다. 반환 되는 값은 [Corsymvarflag](corsymvarflag-enumeration.md) 열거형에 정의 된 값 중 하나입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedVariable 인터페이스](isymunmanagedvariable-interface.md)
