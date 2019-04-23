---
title: IMetaDataImport::GetTypeDefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a482c7a06efe888408206f2de569e0a8739b85b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121513"
---
# <a name="imetadataimportgettypedefprops-method"></a>IMetaDataImport::GetTypeDefProps 메서드
메타 데이터 정보를 반환 합니다 <xref:System.Type> 지정한 TypeDef 토큰이 나타내는입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 [in] 에 대 한 메타 데이터를 반환할 형식을 나타내는 TypeDef 토큰입니다.  
  
 `szTypeDef`  
 [out] 형식 이름을 포함 하는 버퍼입니다.  
  
 `cchTypeDef`  
 [in] 와이드 문자에서 크기 `szTypeDef`합니다.  
  
 `pchTypeDef`  
 [out] 반환 하는 와이드 문자 수가 `szTypeDef`합니다.  
  
 `pdwTypeDefFlags`  
 [out] 형식 정의 수정 된 플래그에 대 한 포인터입니다. 이 값은의 비트 마스크를 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 열거형입니다.  
  
 `ptkExtends`  
 [out] 형식 정의 또는 TypeRef 메타 데이터 토큰 요청 된 형식의 기본 형식을 나타내는입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
