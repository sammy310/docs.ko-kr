---
description: '자세히 알아보기: IMetaDataAssemblyImport:: GetManifestResourceProps 메서드'
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
ms.openlocfilehash: d8f390f8eede5153df282cc30479ceff22fb552d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728288"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>IMetaDataAssemblyImport::GetManifestResourceProps 메서드

지정 된 메타 데이터 시그니처를 사용 하 여 매니페스트 리소스의 속성 집합을 가져옵니다.  
  
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
 진행 `mdManifestResource` 속성을 가져올 리소스를 나타내는 토큰입니다.  
  
 `szName`  
 제한이 리소스의 이름입니다.  
  
 `cchName`  
 진행 와이드 문자의 크기 (와이드 문자)입니다 `szName` .  
  
 `pchName`  
 제한이 에 실제로 반환 된 와이드 문자 수에 대 한 포인터입니다 `szName` .  
  
 `ptkImplementation`  
 제한이 `mdFile` `mdAssemblyRef` 리소스를 포함 하는 파일 또는 어셈블리를 각각 나타내는 토큰 또는 토큰에 대 한 포인터입니다.  
  
 `pdwOffset`  
 제한이 파일 내 리소스의 시작에 대 한 오프셋을 지정 하는 값에 대 한 포인터입니다.  
  
 `pdwResourceFlags`  
 제한이 리소스에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다. Flags 값은 하나 이상의 [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) 값의 조합입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
