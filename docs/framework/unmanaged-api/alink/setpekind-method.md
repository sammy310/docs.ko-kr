---
title: SetPEKind 메서드
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: be8a11cbf70e2c6f19ace67648b124515c1fb3c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680042"
---
# <a name="setpekind-method"></a>SetPEKind 메서드

이식 가능한 실행 파일 유형 (컴퓨터 특정 컴퓨터 또는 컴퓨터 관계 없음)을 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a>매개 변수  

 `AssemblyID`  
 어셈블리의 ID입니다.  
  
 `FileToken`  
 PE 형식을 설정할 파일의 토큰입니다. `AssemblyID`가 바인딩되지 않은 .netmodule을 나타내지 않는 경우 NULL 일 수 있습니다.  
  
 `dwPEKind`  
 [CorPEKind 열거](../metadata/corpekind-enumeration.md)에 표시 되는 PE의 형식입니다.  
  
 `dwMachine`  
 NT 헤더에 표시 된 대상 컴퓨터 아키텍처입니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참조

- [GetPEKind 메서드](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [IALink 인터페이스](ialink-interface.md)
- [ALink API](index.md)
