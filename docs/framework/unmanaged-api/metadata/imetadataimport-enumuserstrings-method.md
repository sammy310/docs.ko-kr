---
title: IMetaDataImport::EnumUserStrings 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
ms.openlocfilehash: c7dcc740dcf9b228713693a57dc8ef96d215ebad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716566"
---
# <a name="imetadataimportenumuserstrings-method"></a>IMetaDataImport::EnumUserStrings 메서드

현재 메타데이터 범위에서 하드 코드된 문자열을 나타내는 String 토큰을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `phEnum`  
 [in, out] 열거자에 대 한 포인터입니다. 이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.  
  
 `rStrings`  
 제한이 문자열 토큰을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 [in] `rStrings` 배열의 최대 크기입니다.  
  
 `pcStrings`  
 제한이 에서 반환 된 문자열 토큰의 수입니다 `rStrings` .  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumUserStrings` 성공적으로 반환 되었습니다.|  
|`S_FALSE`|열거할 토큰이 없습니다. 이 경우는 `pcStrings` 0입니다.|  
  
## <a name="remarks"></a>설명  

 [IMetaDataEmit::D efineUserString](imetadataemit-defineuserstring-method.md) 메서드는 문자열 토큰을 만듭니다. 이 메서드는 컴파일러가 아니라 메타 데이터 브라우저에서 사용 하도록 설계 되었습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
