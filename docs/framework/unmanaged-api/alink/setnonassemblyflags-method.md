---
title: SetNonAssemblyFlags 메서드
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
ms.openlocfilehash: 2dcb363a2a84b3c2e0438e45663b96d9a0f83f61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445545"
---
# <a name="setnonassemblyflags-method"></a>SetNonAssemblyFlags 메서드
어셈블리와 관련 없는 플래그를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `afFlags`  
 ALink 플래그입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink 필요  
  
## <a name="see-also"></a>참고자료

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
