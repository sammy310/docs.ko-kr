---
description: '자세히 알아보기: IMetaDataEmit:: SetParent 메서드'
title: IMetaDataEmit::SetParent 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: 9025d4a37de85a0e657059f63ef781dc4377c036
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772005"
---
# <a name="imetadataemitsetparent-method"></a>IMetaDataEmit::SetParent 메서드

[IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md)에 대 한 이전 호출로 정의 된 지정 된 멤버가 [IMetaDataEmit::D Efin def](imetadataemit-definetypedef-method.md)의 이전 호출에 정의 된 대로 지정 된 형식의 멤버 임을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `mr`  
 진행 `mdMemberRef` 새 부모를 받을 토큰입니다.  
  
 `tk`  
 진행 `mdToken` 새 부모에 대 한입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
