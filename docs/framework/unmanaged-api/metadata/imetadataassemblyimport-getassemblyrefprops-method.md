---
title: IMetaDataAssemblyImport::GetAssemblyRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175969"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps 메서드
지정된 메타데이터 서명을 통해 어셈블리 참조에 대한 속성 집합을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `mdar`  
 【인】 속성을 `mdAssemblyRef` 가져오는 어셈블리 참조를 나타내는 메타데이터 토큰입니다.  
  
 `ppbPublicKeyOrToken`  
 【아웃】 공개 키 또는 메타데이터 토큰에 대한 포인터입니다.  
  
 `pcbPublicKeyOrToken`  
 【아웃】 반환된 공개 키 또는 토큰의 바이트 수입니다.  
  
 `szName`  
 【아웃】 어셈블리의 간단한 이름입니다.  
  
 `cchName`  
 【인】 크기, 와이드 문자, 의 `szName`.  
  
 `pchName`  
 【아웃】 실제로 반환된 와이드 문자 수에 `szName`대한 포인터입니다.  
  
 `pMetaData`  
 【아웃】 어셈블리 메타데이터가 포함된 ASSEMBLYMETADATA 구조에 대한 포인터입니다.  
  
 `ppbHashValue`  
 【아웃】 해시 값에 대한 포인터입니다. 이 해시는 `PublicKey` [어셈블리RefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) 열거형의 arfFullOriginator 플래그가 설정되지 않는 한 참조되는 어셈블리의 속성의 SHA-1 알고리즘을 사용하는 해시입니다.  
  
 `pcbHashValue`  
 【아웃】 반환된 해시 값의 와이드 문자 수입니다.  
  
 `pdwAssemblyRefFlags`  
 【아웃】 어셈블리에 적용된 메타데이터를 설명하는 플래그에 대한 포인터입니다. 플래그 값은 하나 이상의 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 플래그 값의 조합입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 성공하는 경우 S_OK 반환합니다. 그렇지 않으면 Winerror.h 헤더 파일에 정의된 오류 코드 중 하나를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
