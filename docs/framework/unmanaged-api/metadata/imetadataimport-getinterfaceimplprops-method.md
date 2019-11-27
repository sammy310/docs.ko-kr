---
title: IMetaDataImport::GetInterfaceImplProps 메서드
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: e5eb735acac73d694a0719c206bd22711a8c0333
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437545"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>IMetaDataImport::GetInterfaceImplProps 메서드
지정 된 메서드를 구현 하는 <xref:System.Type> 및 해당 메서드를 선언 하는 인터페이스에 대 한 메타 데이터 토큰에 대 한 포인터를 가져옵니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `iiImpl`  
 진행 클래스 및 인터페이스 토큰을 반환할 메서드를 나타내는 메타 데이터 토큰입니다.  
  
 `pClass`  
 제한이 메서드를 구현 하는 클래스를 나타내는 메타 데이터 토큰입니다.  
  
 `ptkIface`  
 제한이 구현 된 메서드를 정의 하는 인터페이스를 나타내는 메타 데이터 토큰입니다.  

## <a name="remarks"></a>설명

 [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) 메서드를 호출 하 여 `iImpl` 값을 가져옵니다.
 
 예를 들어 클래스에 `mdTypeDef` 토큰 값이 0x02000007이 고 해당 형식에 토큰이 있는 세 개의 인터페이스를 구현 한다고 가정 합니다. 

- 0x02000003 (TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C (TypeDef)

개념적으로이 정보는 다음과 같이 인터페이스 구현 테이블에 저장 됩니다.

| 행 번호 | 클래스 토큰 | 인터페이스 토큰 |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

리콜, 토큰은 4 바이트 값입니다.

- 하위 3 바이트는 행 번호 또는 RID를 보유 합니다.
- 상위 바이트는 `mdtInterfaceImpl`에 대 한 토큰 유형-0x09을 보유 합니다.

`GetInterfaceImplProps`는 `iImpl` 인수에서 토큰을 제공 하는 행에 포함 된 정보를 반환 합니다. 
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
