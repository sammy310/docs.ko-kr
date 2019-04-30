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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ab30e1f80be71b42a131afe68e38f0b2731ae60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986104"
---
# <a name="isymunmanagedwriterclosescope-method"></a>ISymUnmanagedWriter::CloseScope 메서드
현재 어휘 범위를 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a>매개 변수  
 `endOffset`  
 [in] 바이트의 어휘 범위에서 마지막 명령의 끝에 있는 점의 메서드 시작 부분 으로부터의 오프셋입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 범위 닫히면 그 이상의 없는 변수를 정의할 수 있습니다.  
  
 [Isymunmanagedwriter:: Openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) 사용 하 여 사용할 수 있는 불투명 한 범위 식별자를 반환 합니다 [isymunmanagedwriter:: Setscoperange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) 나중에 범위를 정의 하의 시작과 끝 오프셋입니다. 이 경우 `ISymUnmanagedWriter::OpenScope` 및 `ISymUnmanagedWriter::CloseScope`에 전달된 오프셋은 무시됩니다. 범위 식별자는 현재 메서드에서만에서 유효 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
