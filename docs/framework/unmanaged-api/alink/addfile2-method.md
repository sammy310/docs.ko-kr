---
description: '자세히 알아보기: AddFile2 메서드'
title: AddFile2 메서드
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
ms.openlocfilehash: d53527ecf7e8b3a99a11ea99512fbc812125de3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638615"
---
# <a name="addfile2-method"></a>AddFile2 메서드

어셈블리에 파일을 추가 합니다. 바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `AssemblyID`  
 파일이 추가 된 어셈블리의 ID입니다.  
  
 `pszFilename`  
 추가할 파일의 이름입니다.  
  
 `dwFlags`  
 `FileDef`및와 같은 COM + 플래그 `ffContainsNoMetaData` `ffWriteable` 입니다. `dwFlags`[DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.  
  
 `pEmitter`  
 [IMetaDataEmit2 인터페이스](../metadata/imetadataemit2-interface.md) 인터페이스에 대 한 인터페이스입니다.  
  
 `pFileToken`  
 추가 되는 파일에 대 한 ID를 받습니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참고 항목

- [IALink2 인터페이스](ialink2-interface.md)
- [IALink 인터페이스](ialink-interface.md)
- [ALink API](index.md)
