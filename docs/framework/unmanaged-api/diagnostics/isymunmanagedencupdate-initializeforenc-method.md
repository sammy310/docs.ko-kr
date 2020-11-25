---
title: ISymUnmanagedENCUpdate::InitializeForEnc 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
ms.openlocfilehash: 96ac27bfd155eaf95b1880c2f4dee0e24330e446
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729046"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a>ISymUnmanagedENCUpdate::InitializeForEnc 메서드

[ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) 메서드를 처음으로 호출 하기 전에 메서드 경계를 계산할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedENCUpdate 인터페이스](isymunmanagedencupdate-interface.md)
