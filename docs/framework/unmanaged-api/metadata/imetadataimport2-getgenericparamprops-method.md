---
title: IMetaDataImport2::GetGenericParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55a765fe3942cbf71a8460187e829dc7f3ca877e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082337"
---
# <a name="imetadataimport2getgenericparamprops-method"></a>IMetaDataImport2::GetGenericParamProps 메서드
지정된 된 토큰을 나타내는 제네릭 매개 변수를 사용 하 여 연결 된 메타 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `gp`  
 [in] 메타 데이터를 반환 하는 제네릭 매개 변수를 나타내는 토큰입니다.  
  
 `pulParamSeq`  
 [out] 서 수 위치는 `Type` 부모 생성자 또는 메서드 매개 변수입니다.  
  
 `pdwParamFlags`  
 [out] 값을 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 설명 하는 열거형은 `Type` 제네릭 매개 변수입니다.  
  
 `ptOwner`  
 [out] 형식 정의 또는 MethodDef 토큰 매개 변수의 소유자를 나타내는입니다.  
  
 `reserved`  
 [out] 향후 확장성을 위해 예약 되어 있습니다.  
  
 `wzName`  
 [out] 제네릭 매개 변수의 이름입니다.  
  
 `cchName`  
 [in] 크기는 `wzName` 버퍼입니다.  
  
 `pchName`  
 [out] 반환 된 크기의 와이드 문자 이름입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
