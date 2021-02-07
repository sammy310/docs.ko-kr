---
description: '자세한 정보: SetAssemblyProps 메서드'
title: SetAssemblyProps 메서드
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
ms.openlocfilehash: 212d8aad22ac1cb231db46f20ff65de2339a21aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662353"
---
# <a name="setassemblyprops-method"></a>SetAssemblyProps 메서드

어셈블리 수준 속성을 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `AssemblyID`  
 어셈블리의 ID입니다.  
  
 `FileToken`  
 속성을 정의 하는 파일입니다. `AssemblyID`가 바인딩되지 않은 .netmodule을 나타내지 않는 경우 NULL 일 수 있습니다.  
  
 `Option`  
 수정할 옵션을 나타냅니다.  
  
 `Value`  
 옵션의 새 값입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참고 항목

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
