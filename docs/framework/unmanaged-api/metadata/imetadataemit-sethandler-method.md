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
ms.openlocfilehash: 6737275fb77e6f177832eb1d96214c37942bcd22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442159"
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler 메서드
지정 된 `IUnknown` 포인터에서 참조 하는 메서드를 토큰 다시 매핑에 대 한 알림 콜백으로 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pUnk`  
 진행 등록할 처리기입니다.  
  
## <a name="remarks"></a>설명  
 메타 데이터 엔진은 `SetHandler`에서 제공 하는 메서드를 사용 하 여 최적화 된 방식으로 레코드를 생성 하지 않고 저장 된 레코드를 최적화 하는 컴파일러로 알림을 보냅니다.  
  
 `SetHandler`를 통해 콜백 메서드를 제공 하지 않는 경우 각 범위에 대해 병합 시 `IMapToken`를 사용 하 여 여러 가져오기 범위가 병합 된 경우를 제외 하 고는 저장 시 최적화가 수행 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
