---
title: IMetaDataImport::EnumCustomAttributes 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: a43c1883038e41cac1b58c78bc26f20d436ebbd1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440244"
---
# <a name="imetadataimportenumcustomattributes-method"></a>IMetaDataImport::EnumCustomAttributes 메서드
지정 된 형식 또는 멤버와 연결 된 사용자 지정 특성 정의 토큰을 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `phEnum`  
 [in, out] 반환 된 열거자에 대 한 포인터입니다.  
  
 `tk`  
 진행 열거형의 범위에 대 한 토큰 이거나 모든 사용자 지정 특성의 경우 0입니다.  
  
 `tkType`  
 진행 열거할 특성 형식의 생성자에 대 한 토큰 이거나, 모든 형식에 대 한 `null`입니다.  
  
 `rCustomAttributes`  
 제한이 사용자 지정 특성 토큰의 배열입니다.  
  
 `cMax`  
 [in] `rCustomAttributes` 배열의 최대 크기입니다.  
  
 `pcCustomAttributes`  
 [out, 선택 사항] `rCustomAttributes`에서 반환 된 실제 토큰 값 수입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` 성공적으로 반환 되었습니다.|  
|`S_FALSE`|열거할 사용자 지정 특성이 없습니다. 이 경우 `pcCustomAttributes`은 0입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
