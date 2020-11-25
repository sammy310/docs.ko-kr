---
title: AddFile 메서드
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 53ca4005f5681cfc5d550301d8aad1406aceb3a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717203"
---
# <a name="addfile-method"></a>AddFile 메서드

어셈블리에 파일을 추가 합니다. 바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `AssemblyID`  
 확대할 어셈블리의 고유 ID입니다.  
  
 `pszFilename`  
 추가할 파일의 정규화 된 이름입니다.  
  
 `dwFlags`  
 및와 같은 COM + FileDef 플래그 `ffContainsNoMetaData` `ffWriteable` 입니다. `dwFlags`[DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.  
  
 `pEmitter`  
 필요한 경우 메타 데이터를 내보내는 데 사용할 [IMetaDataEmit interface](../metadata/imetadataemit-interface.md) 인터페이스입니다.  
  
 `pFileToken`  
 추가 된 파일의 고유 ID가 저장 될 위치에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참조

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
