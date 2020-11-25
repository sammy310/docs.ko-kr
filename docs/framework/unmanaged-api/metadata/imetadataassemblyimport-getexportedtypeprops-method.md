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
ms.openlocfilehash: 32224431051b958a3f01ffeb15cdb6db1dae2657
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722104"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>IMetaDataAssemblyImport::GetExportedTypeProps 메서드

지정 된 메타 데이터 시그니처를 사용 하 여 내보낸 형식의 속성 집합을 가져옵니다.  
  
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
 진행 `mdExportedType` 내보낸 형식을 나타내는 메타 데이터 토큰입니다.  
  
 `szName`  
 제한이 내보낸 형식의 이름입니다.  
  
 `cchName`  
 진행 의 크기 (와이드 문자)입니다 `szName` .  
  
 `pchName`  
 제한이 에서 실제로 반환 된 와이드 문자의 수입니다. `szName`  
  
 `ptkImplementation`  
 제한이 `mdFile` `mdAssemblyRef` `mdExportedType` 내보낸 형식의 속성에 대 한 액세스를 포함 하거나 허용 하는, 또는 메타 데이터 토큰입니다.  
  
 `ptkTypeDef`  
 제한이 `mdTypeDef` 파일의 형식을 나타내는 토큰에 대 한 포인터입니다.  
  
 `pdwExportedTypeFlags`  
 제한이 내보낸 형식에 적용 되는 메타 데이터를 설명 하는 플래그에 대 한 포인터입니다. Flags 값은 하나 이상의 [Cortypeattr](cortypeattr-enumeration.md) 값일 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
