---
title: IMetaDataAssemblyImport::GetManifestResourceProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177657"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>IMetaDataAssemblyImport::GetManifestResourceProps 메서드
지정된 메타데이터 서명을 사용 하 고 매니페스트 리소스의 속성 집합을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mdmr`  
 【인】 속성을 `mdManifestResource` 얻을 리소스를 나타내는 토큰입니다.  
  
 `szName`  
 【아웃】 리소스의 이름입니다.  
  
 `cchName`  
 【인】 크기, 와이드 문자, 의 `szName`.  
  
 `pchName`  
 【아웃】 실제로 반환된 와이드 문자 수에 `szName`대한 포인터입니다.  
  
 `ptkImplementation`  
 【아웃】 리소스를 `mdFile` 포함하는 파일 `mdAssemblyRef` 또는 어셈블리를 각각 나타내는 토큰 또는 토큰에 대한 포인터입니다.  
  
 `pdwOffset`  
 【아웃】 오프셋을 파일 내의 리소스의 시작 부분으로 지정하는 값에 대한 포인터입니다.  
  
 `pdwResourceFlags`  
 【아웃】 리소스에 적용된 메타데이터를 설명하는 플래그에 대한 포인터입니다. 플래그 값은 하나 이상의 [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) 값의 조합입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
