---
title: ImportFile2 메서드
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c6279c790e9b28e5f3bac93d5d0fdd411dd8c0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753488"
---
# <a name="importfile2-method"></a>ImportFile2 메서드
어셈블리 및 바인딩되지 않은 모듈을 가져옵니다. 이 메서드는 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), 되지만 가져올 파일 디스크에 없는 경우 경우에 작동 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `pszFilename`  
 가져올 파일의 이름입니다.  
  
 `pszTargetName`  
 어셈블리에 링크 되어 파일의 이름을 사용할 수 있는 선택적 출력 파일 이름입니다.  
  
 `pAssemblyScopeIn`  
 선택적 범위 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.  
  
 `fSmartImport`  
 TRUE 이면 ImportTypes 되, 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.  
  
 `pImportToken`  
 파일 또는 어셈블리에 대 한 ID를 받습니다.  
  
 `ppAssemblyScope`  
 수신 된 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다. 파일 어셈블리가 아닌 경우 NULL입니다.  
  
 `pdwCountOfScopes`  
 파일 및/또는 가져온 범위 발견을 받습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h가 필요합니다.  
  
## <a name="see-also"></a>참고자료

- [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
