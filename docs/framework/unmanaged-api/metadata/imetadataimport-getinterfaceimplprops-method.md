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
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175384"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>IMetaDataImport::GetInterfaceImplProps 메서드
지정된 메서드를 구현하는 <xref:System.Type> 메서드와 해당 메서드를 선언하는 인터페이스에 대한 메타데이터 토큰에 대한 포인터를 가져옵니다.
  
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
 【인】 클래스 및 인터페이스 토큰을 반환하는 메서드를 나타내는 메타데이터 토큰입니다.  
  
 `pClass`  
 【아웃】 메서드를 구현하는 클래스를 나타내는 메타데이터 토큰입니다.  
  
 `ptkIface`  
 【아웃】 구현된 메서드를 정의하는 인터페이스를 나타내는 메타데이터 토큰입니다.  

## <a name="remarks"></a>설명

 `iImpl` [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) 메서드를 호출 하 여 대 한 값을 가져옵니다.

 예를 들어 클래스에 `mdTypeDef` 토큰 값이 0x0200007이고 형식에 토큰이 있는 세 개의 인터페이스를 구현한다고 가정합니다.

- 0x020000003(TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C(TypeDef)

개념적으로 이 정보는 다음과 같이 인터페이스 구현 테이블에 저장됩니다.

| 행 번호 | 클래스 토큰 | 인터페이스 토큰 |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

토큰은 4바이트 값입니다.

- 3바이트가 낮을수록 행 번호 또는 RID가 유지됩니다.
- 위쪽 바이트는 토큰 형식인 0x09를 보유합니다. `mdtInterfaceImpl`

`GetInterfaceImplProps`은 인수에서 제공하는 토큰행에 있는 `iImpl` 정보를 반환합니다.
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
