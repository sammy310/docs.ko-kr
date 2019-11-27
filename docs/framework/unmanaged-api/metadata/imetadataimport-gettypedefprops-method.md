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
ms.openlocfilehash: c9ac624e17223def206e86fd92ee4fd2de7f6082
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436754"
---
# <a name="imetadataimportgettypedefprops-method"></a>IMetaDataImport::GetTypeDefProps 메서드
지정 된 TypeDef 토큰이 나타내는 <xref:System.Type>에 대 한 메타 데이터 정보를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 진행 메타 데이터를 반환할 형식을 나타내는 TypeDef 토큰입니다.  
  
 `szTypeDef`  
 제한이 형식 이름을 포함 하는 버퍼입니다.  
  
 `cchTypeDef`  
 진행 `szTypeDef`의 와이드 문자 크기입니다.  
  
 `pchTypeDef`  
 제한이 `szTypeDef`에서 반환 되는 와이드 문자 수입니다.  
  
 `pdwTypeDefFlags`  
 제한이 형식 정의를 수정 하는 플래그에 대 한 포인터입니다. 이 값은 [Cortypeattr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 열거형의 비트 마스크입니다.  
  
 `ptkExtends`  
 제한이 요청 된 형식의 기본 형식을 나타내는 TypeDef 또는 TypeRef 메타 데이터 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
