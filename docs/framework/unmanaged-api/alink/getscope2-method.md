---
title: GetScope2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3c11eeeb4eece495a7ccbe51c7e04d077e497ce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494573"
---
# <a name="getscope2-method"></a>GetScope2 메서드
가져오기 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a>매개 변수  
 `AssemblyID`  
 대상 어셈블리의 ID입니다.  
  
 `FileToken`  
 가져올 파일의 ID입니다.  
  
 `dwScope`  
 가져오려는 0부터 시작 범위입니다.  
  
 `ppImportScope`  
 에 대 한 포인터를 받는 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) 표시 된 범위에 대 한 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h가 필요합니다.  
  
## <a name="see-also"></a>참고자료
- [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
