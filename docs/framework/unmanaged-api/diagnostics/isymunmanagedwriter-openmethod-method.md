---
title: ISymUnmanagedWriter::OpenMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: d2d16ab0a29fadd3a64d906a64fc46c422e01c45
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610043"
---
# <a name="isymunmanagedwriteropenmethod-method"></a>ISymUnmanagedWriter::OpenMethod 메서드
기호 정보를 내보내는 메서드를 엽니다. 지정 된 메서드는 시퀀스 위치, 매개 변수 및 어휘 범위를 정의 하는 호출에 대 한 현재 메서드가 됩니다. 전체 메서드 주위에는 암시적 어휘 범위가 있습니다. 이전에 닫힌 메서드를 다시 열면 해당 메서드에 대해 이전에 정의 된 기호가 모두 지워집니다. 한 번에 하나의 개방형 메서드만 있을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a>매개 변수  
 `method`  
 진행 열려는 메서드의 메타 데이터 토큰입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedWriter 인터페이스](isymunmanagedwriter-interface.md)
- [CloseMethod 메서드](isymunmanagedwriter-closemethod-method.md)
- [OpenMethod2 메서드](isymunmanagedwriter3-openmethod2-method.md)
