---
title: ISymUnmanagedScope::GetChildren 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
ms.openlocfilehash: c6d21f40c260890c9c88dcdfccd7e31161024ba3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614866"
---
# <a name="isymunmanagedscopegetchildren-method"></a>ISymUnmanagedScope::GetChildren 메서드
이 범위의 자식을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cChildren`  
 진행 `ULONG32`배열의 크기를 나타내는입니다 `children` .  
  
 `pcChildren`  
 제한이 `ULONG32`자식을 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.  
  
 `children`  
 제한이 반환 된 자식의 배열입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedScope 인터페이스](isymunmanagedscope-interface.md)
- [GetParent 메서드](isymunmanagedscope-getparent-method.md)
