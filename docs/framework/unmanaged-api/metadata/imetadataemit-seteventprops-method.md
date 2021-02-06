---
description: '자세히 알아보기: IMetaDataEmit:: SetEventProps 메서드'
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
ms.openlocfilehash: 888999bc0f80e82e0d139eecac7152a94104ed7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658128"
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps 메서드

[IMetaDataEmit::D efineEvent](imetadataemit-defineevent-method.md)에 대 한 이전 호출에서 정의한 이벤트의 지정 된 기능을 설정 하거나 업데이트 합니다.  
  
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
 진행 이벤트 플래그입니다. 값의 비트 마스크입니다 `CorEventAttr` .  
  
 `tkEventType`  
 진행 이벤트 클래스에 대 한 토큰입니다. `mdTypeDef`또는 `mdTypeRef` 토큰입니다.  
  
 `mdAddOn`  
 진행 이벤트를 구독 하는 데 사용 되는 메서드 이거나 null입니다.  
  
 `mdRemoveOn`  
 진행 이벤트를 구독 취소 하는 데 사용 되는 메서드 이거나 null입니다.  
  
 `mdFire`  
 진행 파생 클래스에서 이벤트를 발생 시키는 데 사용 되는 메서드입니다.  
  
 `rmdOtherMethods[]`  
 진행 이벤트와 연결 된 다른 메서드에 대 한 토큰의 배열입니다. 배열의 마지막 요소는 이어야 합니다 `mdMethodDefNil` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
