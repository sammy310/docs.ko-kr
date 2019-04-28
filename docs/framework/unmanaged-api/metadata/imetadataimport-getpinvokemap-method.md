---
title: IMetaDataImport::GetPinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99aea385cf5e3c8bcf7cf39b7cc5618f99f8a631
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777587"
---
# <a name="imetadataimportgetpinvokemap-method"></a>IMetaDataImport::GetPinvokeMap 메서드
PInvoke 호출의 대상 어셈블리를 나타내는 ModuleRef 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tk`  
 [in] 에 대 한 PInvoke 매핑 메타 데이터를 가져올 FieldDef 또는 MethodDef 토큰입니다.  
  
 `pdwMappingFlags`  
 [out] 매핑에 사용 되는 플래그에 대 한 포인터입니다. 이 값은의 비트 마스크를 [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) 열거형입니다.  
  
 `szImportName`  
 [out] 관리 되지 않는 대상 DLL의 이름입니다.  
  
 `cchImportName`  
 [in] 와이드 문자에서 크기 `szImportName`합니다.  
  
 `pchImportName`  
 [out] 반환 하는 와이드 문자 수가 `szImportName`합니다.  
  
 `pmrImportDLL`  
 [out] 관리 되지 않는 대상 개체 라이브러리를 나타내는 ModuleRef 토큰에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
