---
title: IMetaDataEmit::SetEventProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177522"
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps 메서드
[IMetaDataEmit::DefineEvent에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)대한 사전 호출에 의해 정의된 이벤트의 지정된 기능을 설정하거나 업데이트합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ev`  
 【인】 이벤트 토큰입니다.  
  
 `dwEventFlags`  
 【인】 이벤트 플래그입니다. 이것은 값의 `CorEventAttr` 비트 마스크입니다.  
  
 `tkEventType`  
 【인】 이벤트 클래스의 토큰입니다. 이것은 또는 `mdTypeDef` 토큰입니다. `mdTypeRef`  
  
 `mdAddOn`  
 【인】 이벤트를 구독하는 데 사용되는 메서드 또는 null입니다.  
  
 `mdRemoveOn`  
 【인】 이벤트 구독을 취소하거나 null에 사용되는 메서드입니다.  
  
 `mdFire`  
 【인】 이벤트를 발생시키기 위해 파생 클래스에서 사용하는 메서드입니다.  
  
 `rmdOtherMethods[]`  
 【인】 이벤트와 연결된 다른 메서드에 대한 토큰 배열입니다. 배열의 마지막 요소는 . `mdMethodDefNil`  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
