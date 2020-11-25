---
title: ISymUnmanagedWriter::CloseScope 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 561a6348b9976789b02961fadb37d9127f5a6a13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713043"
---
# <a name="isymunmanagedwriterclosescope-method"></a>ISymUnmanagedWriter::CloseScope 메서드

현재 어휘 범위를 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a>매개 변수  

 `endOffset`  
 진행 어휘 범위에서 마지막 명령의 끝에 있는 지점에서의 오프셋 (바이트)입니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="remarks"></a>설명  

 범위가 닫히면 변수 내에서 더 이상 변수를 정의할 수 없습니다.  
  
 [ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) 는 나중에 범위의 시작 및 끝 오프셋을 정의 하는 [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) 와 함께 사용할 수 있는 불투명 범위 식별자를 반환 합니다. 이 경우 `ISymUnmanagedWriter::OpenScope` 및 `ISymUnmanagedWriter::CloseScope`에 전달된 오프셋은 무시됩니다. 범위 식별자는 현재 메서드에서만 유효 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
