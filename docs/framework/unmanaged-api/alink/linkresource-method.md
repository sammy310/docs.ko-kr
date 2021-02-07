---
description: 다음에 대해 자세히 알아보세요. LinkResource 메서드
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
ms.openlocfilehash: ff12138433577eccbb313b8e64a329be1358ba70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662548"
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
 및와 같은 내게 필요한 옵션 플래그 `mrPublic` `mrPrivate` 입니다. 이 매개 변수는 [DefineManifestResource 메서드에](../metadata/imetadataassemblyemit-definemanifestresource-method.md)전달 될 수 있습니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참고 항목

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
