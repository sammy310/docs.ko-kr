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
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179385"
---
# <a name="setpekind-method"></a>SetPEKind 메서드
컴퓨터별 또는 기계에 구애받지 않는 휴대용 실행 유형이 결정됩니다.  
  
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
 PE 형식을 설정할 파일의 토큰입니다. 언바운드 넷 `AssemblyID` 모듈을 나타내지 않으면 NULL이 될 수 있습니다.  
  
 `dwPEKind`  
 [CorPEKind 열거형에](../metadata/corpekind-enumeration.md)표시된 PE 유형입니다.  
  
 `dwMachine`  
 NT 헤더에 표시된 대로 대상 컴퓨터 아키텍처입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공하면 S_OK 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 alink.h가 필요합니다.  
  
## <a name="see-also"></a>참고 항목

- [GetPEKind 메서드](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [IALink 인터페이스](ialink-interface.md)
- [ALink API](index.md)
