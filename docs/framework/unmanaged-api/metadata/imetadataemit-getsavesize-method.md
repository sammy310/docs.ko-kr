---
title: IMetaDataEmit::GetSaveSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
ms.openlocfilehash: 5cb202f5284c1c18545ec750b2fa0f04d4b0d2e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722065"
---
# <a name="imetadataemitgetsavesize-method"></a>IMetaDataEmit::GetSaveSize 메서드

현재 범위에서 어셈블리의 예상 이진 크기와 해당 메타 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `fSave`  
 진행 정확 하 게 또는 대략적인 크기를 가져올 것인지 여부를 지정 하는 [CorSaveSize](corsavesize-enumeration.md) 열거형의 값입니다. CssAccurate, cssQuick 및 cssDiscardTransientCAs의 세 가지 값만 유효 합니다.  
  
- cssAccurate는 정확한 저장 크기를 반환 하지만 계산 하는 데 더 오래 걸립니다.  
  
- cssQuick은 안전을 위해 채워진 크기를 반환 하지만 계산 하는 데 시간이 더 짧습니다.  
  
- cssDiscardTransientCAs `GetSaveSize` 는 삭제 가능한 사용자 지정 특성을 throw 할 수 있음을 알려 줍니다.  
  
 `pdwSaveSize`  
 제한이 파일을 저장 하는 데 필요한 크기에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `GetSaveSize` 현재 범위에서 어셈블리와 모든 메타 데이터를 저장 하는 데 필요한 공간 (바이트)을 계산 합니다. [IMetaDataEmit:: SaveToStream](imetadataemit-savetostream-method.md) 메서드를 호출 하면이 바이트 수가 생성 됩니다.  
  
 호출자가 [IMapToken](imaptoken-interface.md) 인터페이스를 구현 하는 경우 ( [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) 또는 [IMetaDataEmit:: Merge](imetadataemit-merge-method.md))는 `GetSaveSize` 메타 데이터에 대해 두 개의 패스를 수행 하 여 최적화 하 고 압축 합니다. 그렇지 않으면 최적화가 수행 되지 않습니다.  
  
 최적화를 수행 하는 경우 첫 번째 패스는 단지 메타 데이터 구조를 정렬 하 여 가져오기 시간 검색의 성능을 조정 합니다. 이 단계에서는 일반적으로 레코드를 이동 하 고 나중에 참조할 수 있도록 도구에 의해 유지 된 토큰의 부작용이 발생 합니다. 그러나 메타 데이터는 두 번째 통과 이후까지 이러한 토큰 변경을 호출자에 게 알리지 않습니다. 두 번째 단계에서는 `mdTypeRef` `mdMemberRef` 현재 메타 데이터 범위에 선언 된 형식 또는 멤버에 대 한 참조가 있는 경우 (초기 바인딩) 및 토큰을 최적화 하는 것과 같이 메타 데이터의 전체 크기를 줄이기 위해 다양 한 최적화가 수행 됩니다. 이 패스에는 토큰 매핑의 또 다른 왕복이 발생 합니다. 이 단계를 수행한 후 메타 데이터 엔진은 해당 `IMapToken` 인터페이스를 통해 변경 된 모든 토큰 값의 호출자에 게 알립니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
