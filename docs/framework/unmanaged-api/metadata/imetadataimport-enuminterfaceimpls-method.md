---
title: IMetaDataImport::EnumInterfaceImpls 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: 0b040a2741a44b9d361dabc38c26b8934659003b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711522"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls 메서드

지정 된에 의해 구현 된 모든 인터페이스를 열거 `TypeDef` 합니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `phEnum`  
 [in, out] 열거자에 대 한 포인터입니다.  
  
 `td`  
 진행 인터페이스 구현을 나타내는 MethodDef 토큰이 열거 될 TypeDef의 토큰입니다.  
  
 `rImpls`  
 제한이 MethodDef 토큰을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 진행 배열의 최대 길이 `rImpls` 입니다.  
  
 `pcImpls`  
 제한이 에서 반환 된 실제 토큰 수 `rImpls` 입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` 성공적으로 반환 되었습니다.|  
|`S_FALSE`|열거할 MethodDef 토큰이 없습니다. `pcImpls`이 경우는 0으로 설정 됩니다.|  

## <a name="remarks"></a>설명

열거형은 `mdInterfaceImpl` 지정 된에 의해 구현 되는 각 인터페이스에 대 한 토큰의 컬렉션을 반환 합니다 `TypeDef` . 인터페이스 토큰은 인터페이스가 지정 된 순서 (또는)로 반환 됩니다 `DefineTypeDef` `SetTypeDefProps` . 반환 된 토큰의 속성은 `mdInterfaceImpl` [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)를 사용 하 여 쿼리할 수 있습니다.
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
