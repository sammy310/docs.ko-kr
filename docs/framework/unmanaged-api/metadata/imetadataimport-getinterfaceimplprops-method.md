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
ms.openlocfilehash: 1c9d9647084aa729817eeeb17ee3f5cd320c0d29
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491248"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>IMetaDataImport::GetInterfaceImplProps 메서드
<xref:System.Type>지정 된 메서드를 구현 하는 및 해당 메서드를 선언 하는 인터페이스에 대 한 메타 데이터 토큰에 대 한 포인터를 가져옵니다.
  
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

 `iImpl` [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) 메서드를 호출 하 여의 값을 가져옵니다.

 예를 들어, 클래스의 `mdTypeDef` 토큰 값이 0x02000007이 고 형식에 토큰이 있는 세 개의 인터페이스를 구현 한다고 가정 합니다.

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
- 상위 바이트는 토큰 유형 – 0x09를 보유 `mdtInterfaceImpl` 합니다.

`GetInterfaceImplProps`인수에 제공 하는 토큰을 포함 하는 행에 저장 된 정보를 반환 합니다 `iImpl` .
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
