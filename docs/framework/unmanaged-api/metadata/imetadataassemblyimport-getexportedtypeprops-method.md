---
title: IMetaDataAssemblyImport::GetExportedTypeProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 15b58e01d4ce99f19f510c760819471b84380b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177765"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>IMetaDataAssemblyImport::GetExportedTypeProps 메서드
지정된 메타데이터 서명을 사용 하 고 내보낸된 형식의 속성 집합을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mdct`  
 【인】 내보낸 형식을 나타내는 `mdExportedType` 메타데이터 토큰입니다.  
  
 `szName`  
 【아웃】 내보낸 형식의 이름입니다.  
  
 `cchName`  
 【인】 크기, 넓은 문자, `szName`의 .  
  
 `pchName`  
 【아웃】 실제로 반환된 와이드 문자 의 수`szName`  
  
 `ptkImplementation`  
 【아웃】 내보낸 `mdAssemblyRef`형식의 속성에 대한 액세스를 포함하거나 허용하는 `mdExportedType` `mdFile`메타데이터 토큰입니다.  
  
 `ptkTypeDef`  
 【아웃】 파일의 형식을 `mdTypeDef` 나타내는 토큰에 대한 포인터입니다.  
  
 `pdwExportedTypeFlags`  
 【아웃】 내보낸 형식에 적용된 메타데이터를 설명하는 플래그에 대한 포인터입니다. 플래그 값은 하나 이상의 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 값일 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
