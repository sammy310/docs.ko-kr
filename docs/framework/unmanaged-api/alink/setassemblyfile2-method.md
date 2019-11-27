---
title: SetAssemblyFile2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
ms.openlocfilehash: 4f710ef9741869a2b4fd8473ed3ecf379cfcc56d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445593"
---
# <a name="setassemblyfile2-method"></a>SetAssemblyFile2 메서드
새 어셈블리에 대 한 및 옵션의 이름을 설정 합니다. 바인딩되지 않은 모듈을 생성할 때이 메서드를 호출 하지 마십시오.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `pszFilename`  
 매니페스트 파일의 이름입니다.  
  
 `pEmitter`  
 이 파일에 대 한 [IMetaDataEmit2 interface](../metadata/imetadataemit2-interface.md) 인터페이스입니다.  
  
 `afFlags`  
 [Assemblyflags 열거형](../metadata/assemblyflags-enumeration.md)으로 표시 되는 옵션입니다.  
  
 `pAssemblyID`  
 생성 되는 어셈블리에 대 한 고유 ID를 받습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참고 항목

- [IALink2 인터페이스](ialink2-interface.md)
- [IALink 인터페이스](ialink-interface.md)
- [ALink API](index.md)
