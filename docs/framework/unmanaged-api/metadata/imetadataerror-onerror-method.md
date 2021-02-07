---
description: '자세히 알아보기: IMetaDataError:: OnError 메서드'
title: IMetaDataError::OnError 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
ms.openlocfilehash: 9556f1bd7758755d9160e3a2e91a1fe5786aa562
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670972"
---
# <a name="imetadataerroronerror-method"></a>IMetaDataError::OnError 메서드

메타 데이터 병합 중에 발생 하는 오류에 대 한 알림을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `hrError`  
 진행 호출 하는 메서드에 반환 되는 HRESULT 오류 값입니다.  
  
 `token`  
 진행 오류가 발생 했을 때 병합 되 고 있던 코드 개체의 메타 데이터 토큰입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataError 인터페이스](imetadataerror-interface.md)
