---
title: IMetaDataAssemblyImport::GetAssemblyFromScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
ms.openlocfilehash: adcaac02526c7d72ffb75ba6c7552632173032cf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009043"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a>IMetaDataAssemblyImport::GetAssemblyFromScope 메서드
현재 범위에 있는 어셈블리에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ptkAssembly`  
 제한이 어셈블리를 식별 하는 검색 된 토큰에 대 한 포인터입니다 `mdAssembly` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
