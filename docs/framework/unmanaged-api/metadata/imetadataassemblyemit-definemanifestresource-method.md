---
title: IMetaDataAssemblyEmit::DefineManifestResource 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 5aa5d78faa8ca9261594e2a649b11088e1d78ee7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177863"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>IMetaDataAssemblyEmit::DefineManifestResource 메서드
지정된 매니페스트 리소스에 대한 메타데이터를 포함하는 `ManifestResource` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szName`  
 【인】 리소스의 이름입니다.  
  
 `tkImplementation`  
 【인】 형식 `mdtFile` 또는 `mdtAssemblyRef` 리소스 공급자에 매핑되는 메타데이터 토큰입니다. NULL 값은 메타데이터가 포함된 파일이 리소스 공급자임을 나타냅니다.  
  
 `dwOffset`  
 【인】 파일 내의 리소스의 시작 부분에 대한 오프셋입니다. 독립 실행형 파일의 리소스의 경우 항상 0이 됩니다. 리소스가 PE(이식 가능한 실행 파일) 파일에 포함된 경우 cor.h 헤더 파일에 지정된 위치에서 시작하는 리소스 BLOB의 오프셋입니다.  
  
 `dwResourceFlags`  
 【인】 리소스 정의에 대한 속성 설정을 지정하는 플래그 값의 비트 조합입니다.  
  
 `pmdmr`  
 【아웃】 반환된 메타데이터 토큰에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 어셈블리의 각 파일에 구현되는 각 리소스에 대해 하나의 `ManifestResource` 메타데이터 구조를 정의해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
