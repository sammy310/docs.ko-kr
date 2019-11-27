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
ms.openlocfilehash: 6966d0ad2fefd8401b19d8e8dcf7776799a066b2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432557"
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent 메서드
지정 된 메타 데이터 시그니처를 사용 하 여 이벤트에 대 한 정의를 만들고 해당 이벤트 정의에 대 한 토큰을 가져옵니다.  
  
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
 진행 대상 클래스 또는 인터페이스에 대 한 토큰입니다. `mdTypeDef` 또는 `mdTypeDefNil` 토큰입니다.  
  
 `szEvent`  
 진행 이벤트의 이름입니다.  
  
 `dwEventFlags`  
 진행 이벤트 플래그입니다.  
  
 `tkEventType`  
 진행 이벤트 클래스에 대 한 토큰입니다. `mdTypeDef`, `mdTypeRef`또는 `mdTokenNil` 토큰입니다.  
  
 `mdAddOn`  
 진행 이벤트를 구독 하는 데 사용 되는 메서드 이거나 null입니다.  
  
 `mdRemoveOn`  
 진행 이벤트를 구독 취소 하는 데 사용 되는 메서드 이거나 null입니다.  
  
 `mdFire`  
 진행 파생 클래스에서 이벤트를 발생 시키는 데 사용 되는 메서드입니다.  
  
 `rmdOtherMethods[]`  
 진행 이벤트와 연결 된 다른 메서드에 대 한 토큰의 배열입니다. 배열이 `mdMethodDefNil` 토큰으로 종료 되었습니다.  
  
 `pmdEvent`  
 제한이 이벤트에 할당 된 메타 데이터 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
