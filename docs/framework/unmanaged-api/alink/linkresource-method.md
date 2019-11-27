---
title: LinkResource 메서드
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: 9e91d990a8f23335248043c59eb210e8c4155e3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445623"
---
# <a name="linkresource-method"></a>LinkResource 메서드
리소스의 링크입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `AssemblyID`  
 어셈블리의 ID입니다.  
  
 `pszFileName`  
 파일의 이름입니다.  
  
 `pszNewLocation`  
 선택적 새 파일 이름입니다. NULL이 아닌 경우 `pszFileName` pszNewLocation에 복사 됩니다.  
  
 `pszResourceName`  
 리소스의 이름입니다.  
  
 `dwFlags`  
 `mrPublic` 및 `mrPrivate`와 같은 내게 필요한 옵션 플래그입니다. 이 매개 변수는 [DefineManifestResource 메서드에](../metadata/imetadataassemblyemit-definemanifestresource-method.md)전달 될 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참고 항목

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
