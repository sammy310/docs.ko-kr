---
title: FreeWin32ResBlob 메서드
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
ms.openlocfilehash: 2b1addc752c7238116e072c6e957d2b277ceb1e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449395"
---
# <a name="freewin32resblob-method"></a>FreeWin32ResBlob 메서드
Releases the Win32 resource blob and associated resources.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppResBlob`  
 The resource blob to be released. This method assigns the blob pointer to NULL.  
  
## <a name="return-value"></a>반환 값  
 Returns S_OK if the method succeeds.  
  
## <a name="requirements"></a>요구 사항  
 Requires alink.h  
  
## <a name="see-also"></a>참조

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
