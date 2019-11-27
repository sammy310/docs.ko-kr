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
ms.openlocfilehash: 506e13ad956a01b16e36d8c71737fe0efce4c01b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450326"
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps 메서드
[IMetaDataEmit::D efineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)에 대 한 이전 호출에서 정의한 이벤트의 지정 된 기능을 설정 하거나 업데이트 합니다.  
  
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
 진행 이벤트 토큰입니다.  
  
 `dwEventFlags`  
 진행 이벤트 플래그입니다. `CorEventAttr` 값의 비트 마스크입니다.  
  
 `tkEventType`  
 진행 이벤트 클래스에 대 한 토큰입니다. `mdTypeDef` 또는 `mdTypeRef` 토큰입니다.  
  
 `mdAddOn`  
 진행 이벤트를 구독 하는 데 사용 되는 메서드 이거나 null입니다.  
  
 `mdRemoveOn`  
 진행 이벤트를 구독 취소 하는 데 사용 되는 메서드 이거나 null입니다.  
  
 `mdFire`  
 진행 파생 클래스에서 이벤트를 발생 시키는 데 사용 되는 메서드입니다.  
  
 `rmdOtherMethods[]`  
 진행 이벤트와 연결 된 다른 메서드에 대 한 토큰의 배열입니다. 배열의 마지막 요소는 `mdMethodDefNil`이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
