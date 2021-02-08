---
description: '자세히 알아보기: IMetaDataAssemblyImport:: GetAssemblyRefProps 메서드'
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
ms.openlocfilehash: f7011806920ba37ca84b1a48f12da3a5557fa464
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784134"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps 메서드

지정 된 메타 데이터 시그니처를 사용 하는 어셈블리 참조의 속성 집합을 가져옵니다.  
  
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
 진행 `mdAssemblyRef` 속성을 가져올 어셈블리 참조를 나타내는 메타 데이터 토큰입니다.  
  
 `ppbPublicKeyOrToken`  
 제한이 공개 키 또는 메타 데이터 토큰에 대 한 포인터입니다.  
  
 `pcbPublicKeyOrToken`  
 제한이 반환 된 공개 키 또는 토큰의 바이트 수입니다.  
  
 `szName`  
 제한이 어셈블리의 단순한 이름입니다.  
  
 `cchName`  
 진행 와이드 문자의 크기 (와이드 문자)입니다 `szName` .  
  
 `pchName`  
 제한이 에 실제로 반환 된 와이드 문자 수에 대 한 포인터입니다 `szName` .  
  
 `pMetaData`  
 제한이 어셈블리 메타 데이터를 포함 하는 ASSEMBLYMETADATA 구조체에 대 한 포인터입니다.  
  
 `ppbHashValue`  
 제한이 해시 값에 대 한 포인터입니다. 이는 `PublicKey` [Assemblyrefflags](assemblyrefflags-enumeration.md) 열거의 arfFullOriginator 플래그가 설정 되지 않은 경우 참조 되는 어셈블리의 속성에 대 한 sha-1 알고리즘을 사용 하는 해시입니다.  
  
 `pcbHashValue`  
 제한이 반환 된 해시 값의 와이드 문자 수입니다.  
  
 `pdwAssemblyRefFlags`  
 제한이 어셈블리에 적용 된 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다. Flags 값은 하나 이상의 [Corassemblyflags](corassemblyflags-enumeration.md) 값의 조합입니다.  
  
## <a name="return-value"></a>Return Value  

 성공 하면이 메서드는 S_OK를 반환 합니다. 그렇지 않으면 Winerror.h 헤더 파일에 정의 된 오류 코드 중 하나를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
