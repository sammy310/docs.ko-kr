---
description: '자세히 알아보기: IMetaDataAssemblyImport:: FindExportedTypeByName 메서드'
title: IMetaDataAssemblyImport::FindExportedTypeByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: 4a2dc2b65b7f7fe6d5f2e120c635214d457991bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677992"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a>IMetaDataAssemblyImport::FindExportedTypeByName 메서드

이름 및 바깥쪽 형식이 지정 된 경우 내보낸 형식에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szName`  
 진행 내보낸 형식의 이름입니다.  
  
 `mdtExportedType`  
 진행 내보낸 형식의 바깥쪽 클래스에 대 한 메타 데이터 토큰입니다. `mdExportedTypeNil`요청 된 내보낸 형식이 중첩 형식이 아닌 경우이 값은입니다.  
  
 `ptkExportedType`  
 제한이 내보낸 형식을 나타내는 토큰에 대 한 포인터입니다 `mdExportedType` .  
  
## <a name="remarks"></a>설명  

 `FindExportedTypeByName`메서드는 참조를 확인 하기 위해 공용 언어 런타임에서 사용 하는 표준 규칙을 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
- [런타임에서 어셈블리를 찾는 방법](../../deployment/how-the-runtime-locates-assemblies.md)
