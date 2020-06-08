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
ms.openlocfilehash: 6346b1e34e508e5c173bfd0119ac7451d7eef40e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490798"
---
# <a name="imetadataimportgettypedefprops-method"></a>IMetaDataImport::GetTypeDefProps 메서드
지정 된 TypeDef 토큰이 나타내는에 대 한 메타 데이터 정보를 반환 합니다 <xref:System.Type> .  
  
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
 진행 의 와이드 문자 크기입니다 `szTypeDef` .  
  
 `pchTypeDef`  
 제한이 에서 반환 되는 와이드 문자 수입니다 `szTypeDef` .  
  
 `pdwTypeDefFlags`  
 제한이 형식 정의를 수정 하는 플래그에 대 한 포인터입니다. 이 값은 [Cortypeattr](cortypeattr-enumeration.md) 열거형의 비트 마스크입니다.  
  
 `ptkExtends`  
 제한이 요청 된 형식의 기본 형식을 나타내는 TypeDef 또는 TypeRef 메타 데이터 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
