---
description: '자세히 알아보기: IEnumDefinitionIdentity 인터페이스'
title: IEnumDefinitionIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
ms.openlocfilehash: 1055031c064115410334bbe4b20b48deee7ec4c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800164"
---
# <a name="ienumdefinitionidentity-interface"></a>IEnumDefinitionIdentity 인터페이스

개체의 컬렉션에 대 한 열거자 역할을 `IDefinitionIdentity` 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|`IEnumDefinitionIdentity`이와 동일한 멤버를 포함 하는 새 개체에 대 한 인터페이스 포인터를 가져옵니다 `IEnumDefinitionIdentity` .|  
|`IEnumDefinitionIdentity::Next`|현재 위치에서 시작 하 여 지정 된 수의 `IDefinitionIdentity` 개체를 가져옵니다.|  
|`IEnumDefinitionIdentity::Reset`|명령 포인터를이의 시작 부분으로 이동 합니다 `IEnumDefinitionIdentity` .|  
|`IEnumDefinitionIdentity::Skip`|명령 포인터를 현재 위치에서 시작 하 여 지정 된 요소 수 만큼 앞으로 이동 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [Fusion 인터페이스](fusion-interfaces.md)
- [IDefinitionIdentity 인터페이스](idefinitionidentity-interface.md)
