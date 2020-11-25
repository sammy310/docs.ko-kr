---
title: ISymUnmanagedENCUpdate::GetLocalVariables 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: 9e907450b4ae985ee30d9958eec8baba797b495a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728604"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a>ISymUnmanagedENCUpdate::GetLocalVariables 메서드

지역 변수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a>매개 변수  

 `mdMethodToken`  
 진행 메서드의 메타 데이터 토큰입니다.  
  
 `cLocals`  
 진행 `ULONG` 매개 변수의 크기를 나타내는입니다 `rgLocals` .  
  
 `rgLocals`  
 제한이 반환 된 [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) 인스턴스의 배열입니다.  
  
 `pceltFetched`  
 제한이 `ULONG` 로컬을 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다 `rgLocals` .  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedENCUpdate 인터페이스](isymunmanagedencupdate-interface.md)
