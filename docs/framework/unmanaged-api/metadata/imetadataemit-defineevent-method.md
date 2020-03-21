---
title: IMetaDataEmit::DefineEvent 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175852"
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent 메서드
지정된 메타데이터 시그니처가 있는 이벤트에 대한 정의를 만들고 해당 이벤트 정의에 대한 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 【인】 대상 클래스 또는 인터페이스에 대한 토큰입니다. 이것은 또는 `mdTypeDefNil` `mdTypeDef` 토큰입니다.  
  
 `szEvent`  
 【인】 이벤트의 이름입니다.  
  
 `dwEventFlags`  
 【인】 이벤트 플래그입니다.  
  
 `tkEventType`  
 【인】 이벤트 클래스의 토큰입니다. 이것은 `mdTypeDef`. `mdTypeRef` `mdTokenNil`  
  
 `mdAddOn`  
 【인】 이벤트를 구독하는 데 사용되는 메서드 또는 null입니다.  
  
 `mdRemoveOn`  
 【인】 이벤트 구독을 취소하거나 null에 사용되는 메서드입니다.  
  
 `mdFire`  
 【인】 이벤트를 발생시키기 위해 파생 클래스에서 사용하는 메서드입니다.  
  
 `rmdOtherMethods[]`  
 【인】 이벤트와 연결된 다른 메서드에 대한 토큰 배열입니다. 배열은 토큰으로 `mdMethodDefNil` 종료됩니다.  
  
 `pmdEvent`  
 【아웃】 이벤트에 할당된 메타데이터 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
