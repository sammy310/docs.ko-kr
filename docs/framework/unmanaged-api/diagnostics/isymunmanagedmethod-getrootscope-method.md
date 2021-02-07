---
description: '자세히 알아보기: ISymUnmanagedMethod:: GetRootScope 메서드'
title: ISymUnmanagedMethod::GetRootScope 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: b1e490d8e0c5e0d60143202dd0291237685c950f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710008"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a>ISymUnmanagedMethod::GetRootScope 메서드

이 메서드 내에서 루트 어휘 범위를 가져옵니다. 이 범위는 전체 메서드를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pRetVal`  
 제한이 반환 된 [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface로 설정 된 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedMethod 인터페이스](isymunmanagedmethod-interface.md)
