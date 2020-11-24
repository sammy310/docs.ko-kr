---
title: CorMethodSemanticsAttr 열거형
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 347b323951b0125ffa5f82626b2d9b235079492c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676948"
---
# <a name="cormethodsemanticsattr-enumeration"></a>CorMethodSemanticsAttr 열거형

메서드와 관련 속성 또는 이벤트 간의 관계를 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`msSetter`|메서드가 `set` 속성의 접근자 임을 지정 합니다.|  
|`msGetter`|메서드가 `get` 속성의 접근자 임을 지정 합니다.|  
|`msOther`|메서드가 속성 또는 여기에 정의 된 이벤트 이외의 이벤트와 관계가 있음을 지정 합니다.|  
|`msAddOn`|메서드가 이벤트에 대 한 처리기 메서드를 추가 하도록 지정 합니다.|  
|`msRemoveOn`|메서드가 이벤트에 대 한 처리기 메서드를 제거 하도록 지정 합니다.|  
|`msFire`|메서드가 이벤트를 발생 하도록 지정 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 열거형](metadata-enumerations.md)
