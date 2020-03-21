---
title: IMetaDataAssemblyImport::GetAssemblyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: dfa900e2184a8c415d75f5702c572b14c4018749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177792"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>IMetaDataAssemblyImport::GetAssemblyProps 메서드
지정된 메타데이터 서명을 통해 어셈블리에 대한 속성 집합을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mda`  
 [에서]. 속성을 `mdAssembly` 가져오는 어셈블리를 나타내는 메타데이터 토큰입니다.  
  
 `ppbPublicKey`  
 【아웃】 공개 키 또는 메타데이터 토큰에 대한 포인터입니다.  
  
 `pcbPublicKey`  
 【아웃】 반환된 공개 키의 바이트 수입니다.  
  
 `pulHashAlgId`  
 【아웃】 어셈블리의 파일을 해시하는 데 사용되는 알고리즘에 대한 포인터입니다.  
  
 `szName`  
 【아웃】 어셈블리의 간단한 이름입니다.  
  
 `cchName`  
 【인】 크기, 와이드 문자, 의 `szName`.  
  
 `pchName`  
 【아웃】 와이드 문자의 수는 실제로 `szName`에 반환됩니다.  
  
 `pMetaData`  
 【아웃】 어셈블리 메타데이터가 포함된 ASSEMBLYMETADATA 구조에 대한 포인터입니다.  
  
 `pdwAssemblyFlags`  
 【아웃】 어셈블리에 적용된 메타데이터를 설명하는 플래그입니다. 이 값은 하나 이상의 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 플래그 값의 조합입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
