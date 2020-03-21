---
title: IMetaDataEmit::SetHandler 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 375c4b2cece0bdfd763ae383c5412c9e25614baf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177535"
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler 메서드
지정된 `IUnknown` 포인터에서 참조하는 메서드를 토큰 다시 매핑에 대한 알림 콜백으로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pUnk`  
 【인】 등록할 처리기입니다.  
  
## <a name="remarks"></a>설명  
 메타데이터 엔진은 `SetHandler`에서 제공하는 메서드를 사용하여 최적화된 방식으로 레코드를 생성하지 않고 저장된 레코드를 최적화하려는 컴파일러에 알림을 보냅니다.  
  
 콜백 메서드를 통해 `SetHandler`제공 되지 않는 경우 각 범위에 대 한 병합을 사용 하 `IMapToken` 여 여러 가져오기 범위를 병합 하는 경우를 제외 하 고 저장에 최적화가 수행 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
