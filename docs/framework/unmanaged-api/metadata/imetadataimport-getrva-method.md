---
title: IMetaDataImport::GetRVA 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 58ab9ee9381fce4d7af1910df6c8d3bb813bcf13
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490894"
---
# <a name="imetadataimportgetrva-method"></a>IMetaDataImport::GetRVA 메서드
지정 된 토큰이 나타내는 메서드나 필드의 RVA (상대 가상 주소) 및 구현 플래그를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tk`  
 진행 RVA를 반환할 코드 개체를 나타내는 MethodDef 또는 FieldDef 메타 데이터 토큰입니다. 토큰이 FieldDef 경우 필드는 전역 변수 여야 합니다.  
  
 `pulCodeRVA`  
 제한이 토큰이 나타내는 코드 개체의 상대 가상 주소에 대 한 포인터입니다.  
  
 `pdwImplFlags`  
 제한이 메서드에 대 한 구현 플래그에 대 한 포인터입니다. 이 값은 [Cormethodimpl](cormethodimpl-enumeration.md) 열거형의 비트 마스크입니다. 값은 `pdwImplFlags` 가 MethodDef 토큰 인 경우에만 유효 합니다 `tk` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
