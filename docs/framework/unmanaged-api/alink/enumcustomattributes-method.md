---
title: EnumCustomAttributes 메서드
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: 445c833d10631341ef7ad579eaff8ddd96be3428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684852"
---
# <a name="enumcustomattributes-method"></a>EnumCustomAttributes 메서드

어셈블리 수준 사용자 지정 특성을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `hEnum`  
 열거자의 핸들입니다.  
  
 `tkType`  
 열거할 특성의 형식입니다. `mdTokenNill`모든 특성에 대해를 사용 합니다.  
  
 `rCustomValues`  
 사용자 지정 특성 토큰을 받습니다.  
  
 `cMax`  
 배열의 크기를 지정 합니다 `rCustomValues` .  
  
 `pcCustomValues`  
 필요에 따라 토큰 값의 개수를 받습니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink 필요  
  
## <a name="see-also"></a>참조

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
