---
description: '자세히 알아보기: IMetaDataAssemblyImport:: GetAssemblyProps 메서드'
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
ms.openlocfilehash: 9cd3674dcd640bce27ae5d399d0f7de0c2eeca48
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784147"
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
 [in]. `mdAssembly`속성을 가져올 어셈블리를 나타내는 메타 데이터 토큰입니다.  
  
 `ppbPublicKey`  
 제한이 공개 키 또는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `pcbPublicKey`  
 제한이 반환 된 공개 키의 바이트 수입니다.  
  
 `pulHashAlgId`  
 제한이 어셈블리의 파일을 해시 하는 데 사용 되는 알고리즘에 대 한 포인터입니다.  
  
 `szName`  
 제한이 어셈블리의 단순한 이름입니다.  
  
 `cchName`  
 진행 와이드 문자의 크기 (와이드 문자)입니다 `szName` .  
  
 `pchName`  
 제한이 에서 실제로 반환 되는 와이드 문자 수입니다 `szName` .  
  
 `pMetaData`  
 제한이 어셈블리 메타 데이터를 포함 하는 ASSEMBLYMETADATA 구조체에 대 한 포인터입니다.  
  
 `pdwAssemblyFlags`  
 제한이 어셈블리에 적용 된 메타 데이터를 설명 하는 플래그입니다. 이 값은 하나 이상의 [Corassemblyflags](corassemblyflags-enumeration.md) 값의 조합입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
