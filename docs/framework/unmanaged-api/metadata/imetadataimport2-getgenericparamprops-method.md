---
title: IMetaDataImport2::GetGenericParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 16f69d571ffed87a2e848124ce16ac942d319c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702695"
---
# <a name="imetadataimport2getgenericparamprops-method"></a>IMetaDataImport2::GetGenericParamProps 메서드

지정 된 토큰이 나타내는 제네릭 매개 변수와 연결 된 메타 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `gp`  
 진행 메타 데이터를 반환할 제네릭 매개 변수를 나타내는 토큰입니다.  
  
 `pulParamSeq`  
 제한이 `Type` 부모 생성자 또는 메서드에 있는 매개 변수의 서 수 위치입니다.  
  
 `pdwParamFlags`  
 제한이 제네릭 매개 변수에 대 한를 설명 하는 [Corgenericparamattr](corgenericparamattr-enumeration.md) 열거형의 값입니다 `Type` .  
  
 `ptOwner`  
 제한이 매개 변수의 소유자를 나타내는 TypeDef 또는 MethodDef 토큰입니다.  
  
 `reserved`  
 제한이 향후 확장성을 위해 예약 되었습니다.  
  
 `wzName`  
 제한이 제네릭 매개 변수의 이름입니다.  
  
 `cchName`  
 진행 버퍼의 크기 `wzName` 입니다.  
  
 `pchName`  
 제한이 반환 된 이름의 크기 (와이드 문자)입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
