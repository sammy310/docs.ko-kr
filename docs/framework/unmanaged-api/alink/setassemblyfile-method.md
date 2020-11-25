---
title: SetAssemblyFile 메서드
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 45eed17b91f70d4188d1d89fc91a41455f3e845b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732647"
---
# <a name="setassemblyfile-method"></a>SetAssemblyFile 메서드

빌드할 어셈블리의 이름을 할당 합니다. 바인딩되지 않은 모듈을 생성할 때 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `pszFilename`  
 매니페스트 파일의 정규화 된 이름입니다.  
  
 `pEmitter`  
 [IMetaDataEmit interface](../metadata/imetadataemit-interface.md) 인터페이스에 대 한 포인터입니다.  
  
 `afFlags`  
 [Assemblyflags 열거형](../metadata/assemblyflags-enumeration.md)에 정의 된 플래그입니다.  
  
 `pAssemblyID`  
 결과 어셈블리의 ID에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참조

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
