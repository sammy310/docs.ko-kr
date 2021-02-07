---
description: '자세히 알아보기: PreCloseAssembly 메서드'
title: PreCloseAssembly 메서드
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
ms.openlocfilehash: 088a5bba654b3442da64672991d76537e9b4722c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662522"
---
# <a name="precloseassembly-method"></a>PreCloseAssembly 메서드

어셈블리 파일을 닫습니다. 다른 모든 파일을 닫은 후 어셈블리 파일을 닫기 전에이 메서드를 호출 합니다. 바인딩되지 않은 모듈에 대해이 메서드를 호출 하지 마십시오.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `AssemblyID`  
 어셈블리의 ID입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참고 항목

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
