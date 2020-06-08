---
title: IMetaDataImport::GetCustomAttributeByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: e6921a0f6420546ba1e866e37a7a7cb129a77c67
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491461"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>IMetaDataImport::GetCustomAttributeByName 메서드
이름 및 소유자가 지정 된 경우 사용자 지정 특성을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tkObj`  
 진행 사용자 지정 특성을 소유 하는 개체를 나타내는 메타 데이터 토큰입니다.  
  
 `szName`  
 진행 사용자 지정 특성의 이름입니다.  
  
 `ppData`  
 제한이 사용자 지정 특성 값에 해당 하는 데이터 배열에 대 한 포인터입니다.  
  
 `pcbData`  
 제한이 *에서 반환 된 데이터의 크기 (바이트)입니다 `ppData` .  
  
## <a name="remarks"></a>설명  
 동일한 소유자에 대해 여러 사용자 지정 특성을 정의 하는 것은 유효 합니다. 동일한 이름을 가진 경우도 있습니다. 그러나는 `GetCustomAttributeByName` 인스턴스를 하나만 반환 합니다. `GetCustomAttributeByName`는 발견 된 첫 번째 인스턴스를 반환 합니다. 사용자 지정 특성의 모든 인스턴스를 찾으려면 [IMetaDataImport:: EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md) 메서드를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
