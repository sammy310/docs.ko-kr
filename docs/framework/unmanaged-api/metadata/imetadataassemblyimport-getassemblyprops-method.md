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
ms.openlocfilehash: c3c57074ae53e2e1d8d41aa04cb6eb6089db58b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449435"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>IMetaDataAssemblyImport::GetAssemblyProps 메서드
지정 된 메타 데이터 시그니처를 사용 하 여 어셈블리에 대 한 속성 집합을 가져옵니다.  
  
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
 [in]. 속성을 가져올 어셈블리를 나타내는 `mdAssembly` 메타 데이터 토큰입니다.  
  
 `ppbPublicKey`  
 제한이 공개 키 또는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `pcbPublicKey`  
 제한이 반환 된 공개 키의 바이트 수입니다.  
  
 `pulHashAlgId`  
 제한이 어셈블리의 파일을 해시 하는 데 사용 되는 알고리즘에 대 한 포인터입니다.  
  
 `szName`  
 제한이 어셈블리의 단순한 이름입니다.  
  
 `cchName`  
 진행 `szName`의 크기 (와이드 문자)입니다.  
  
 `pchName`  
 제한이 `szName`에서 실제로 반환 되는 와이드 문자 수입니다.  
  
 `pMetaData`  
 제한이 어셈블리 메타 데이터를 포함 하는 ASSEMBLYMETADATA 구조체에 대 한 포인터입니다.  
  
 `pdwAssemblyFlags`  
 제한이 어셈블리에 적용 된 메타 데이터를 설명 하는 플래그입니다. 이 값은 하나 이상의 [Corassemblyflags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 값의 조합입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
