---
title: IHostFilter::MarkToken 메서드
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: 6f8df824ed36b7793d5f07e5b5cf51f65f9c8e24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432232"
---
# <a name="ihostfiltermarktoken-method"></a>IHostFilter::MarkToken 메서드
지정 된 메타 데이터 토큰이 처리 됨을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tk`  
 진행 처리할 메타 데이터 토큰입니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 토큰은 메타 데이터 범위에 있는 경우 처리 하도록 하려고 합니다. `MarkToken` 메서드는 [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) 메서드를 통해 메타 데이터 엔진에 전달 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IHostFilter 인터페이스](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
