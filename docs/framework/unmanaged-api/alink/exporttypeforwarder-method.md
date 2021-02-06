---
description: 다음에 대해 자세히 알아보세요. ExportTypeForwarder 메서드
title: ExportTypeForwarder 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
ms.openlocfilehash: 59fb74c83f6d30dda87d908353795fb218190022
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637991"
---
# <a name="exporttypeforwarder-method"></a>ExportTypeForwarder 메서드

지정 된 어셈블리의 형식 테이블에 형식 전달자를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `tkAssemblyRef`  
 형식 전달 자가 참조 하는 어셈블리에 대 한 참조입니다.  
  
 `pszTypename`  
 내보낼 정규화 된 형식 이름입니다.  
  
 `dwFlags`  
 `ComType` 또는와 같은 `tdPublic` 플래그 `tdNested` 입니다. 이 값은 [DefineExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달 될 수 있습니다.  
  
 `pType`  
 내보낸 형식의 토큰을 받습니다. 중첩 된 형식을 내보내는 경우에만 필요 합니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink 필요  
  
## <a name="see-also"></a>참고 항목

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
